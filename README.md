# Road Accident Analysis
Learning Source: https://www.youtube.com/watch?v=Hn9f13uoLAQ&ab_channel=DataTutorials

Data Source: https://drive.google.com/drive/folders/1pCNs-TRPznlbAn712gAGy7XfBnWs2QJm
## Dashboard Summary
The Road Accident Analysis dashboard provides a comprehensive overview of road accident statistics. It captures key metrics related to casualties, accident trends, and other contributing factors such as vehicle type, location, light conditions, and road types. The data compares Current Year (CY) to Previous Year (PY), highlighting significant changes and patterns in road safety outcomes.
## Dashboard Requirements
- Primary KPI's - Total Casualties and Total Accident values for Current Year and YoY Growth
- Primary KPI's - Total Casualties by Accident Severity for Current Year and YoY Growth
- Secondary KPI's - Total Casualties with respect to Vehicle Type for Current Year
- Monthly Trend showing comparison of Casualties for Current Year and Previous Year
- Casualties by Road Type for Current Year
- Current Year Casualties by Area/Location & Day/Night
- Total Casualties and Total Accident by Location
## DAX Formulas Used in Measures
1. Total Casualties For Current Year and Year on Year Growth

    (a) Current Year To Date Casualties -- CY Casualties Measure

        CY Casualties = TOTALYTD(SUM(Data[Number_of_Casualties]), 'Calendar'[Date])

    (b) Previous Year Casualties -- PY Casualties Measure
  
        PY Casualties = CALCULATE(SUM(Data[Number_of_Casualties]), SAMEPERIODLASTYEAR('Calendar'[Date]))
  
    (c) Year on Year Growth of Casualties - YoY Casualties Measure
  
        YoY Casualties = ([CY Casualties] - [PY Casualties])/[PY Casualties]
3. Total Accidents for Current Year and Year on Year Growth
   
    (a) Current Year Accidents Count -- CY Accidents Count Measure
   
        CY Accidents Count = TOTALYTD(COUNT(Data[Accident_Index]), 'Calendar'[Date])
   
    (b) Previous Year Accidents Count -- PY Accidents Count Measure
   
        PY Accidents Count = CALCULATE(COUNT(Data[Accident_Index]), SAMEPERIODLASTYEAR('Calendar'[Date]))
   
    (c) Year on Year Growth of Accidents - YoY Accidents Measure
   
        YoY Accidents = ([CY Accidents Count]-[PY Accidents Count])/[PY Accidents Count]

## Key Observations
![Road Accident Power BI Dashboard](https://github.com/user-attachments/assets/a6651c00-a557-4cb5-bdf3-74efe472ab26)
### 1. Overall Casualties and Accidents:
Total CY casualties: 195.7K, down by 11.9% compared to PY.
Total CY accidents: 144.4K, reduced by 11.7%, indicating a positive trend in safety measures.
### 2. Severity of Casualties:
Fatal casualties: 2.9K, a slight increase of 3.2% from PY.
Serious casualties: 27K, decreased by 16.2%.
Slight casualties: 165.8K, reduced by 10.6%.
While overall casualties have declined, the rise in fatal cases suggests a need to investigate severe accidents' root causes.
### 3. Casualties by Vehicle Type:
Cars contributed the highest number of casualties (155,804), followed by vans (15,905) and bikes (15,610).
Agricultural vehicles had the least number of casualties (399).
### 4. Casualties by Road Type:
Single carriageways are the most accident-prone roads, with the highest number of casualties.
Dual carriageways, roundabouts, and slip roads report significantly fewer accidents.
Urban vs Rural Analysis:
Urban areas accounted for 61.23% of the casualties, whereas rural areas contributed 38.77%.
Urban zones are significantly more prone to accidents, likely due to higher traffic density.
### 5. Light Conditions:
The majority of accidents (73.84%) occurred in daylight, while 26.16% occurred in dark conditions.
This emphasizes that accidents are not restricted to poor visibility conditions.
### 6. Location Hotspots:
The geographic heat map highlights regions across the UK where accidents are concentrated. Major cities like London, Manchester, and Birmingham appear to have higher accident densities.
### 7. Casualties Monthly Trend:
Casualty trends for CY 2022 show a fluctuating pattern, but overall lower compared to PY 2021.
Peak months for accidents occur in mid-year, suggesting possible seasonal impacts or increased travel activity.

## Recommendations
- Target Urban Areas: Implement stricter traffic regulations, surveillance, and awareness campaigns in urban regions to reduce the high casualty rates.
- Address Fatality Causes: Investigate and mitigate factors causing the increase in fatal accidents, such as speeding or poor emergency response.
- Enhance Safety on Single Carriageways: Introduce better signage, barriers, and speed controls on single carriageways where most casualties occur.
- Vehicle-Specific Strategies: Tailor safety interventions for high-risk vehicle types, especially cars and bikes.
- Daytime Accident Focus: Despite better visibility, daytime accidents dominate. This calls for campaigns targeting distracted driving, pedestrian safety, and road sharing etiquette.


* Thank you to Data Tutorials Channel for providing the source material on road accident analysis; I truly appreciate the effort and insights shared, which have greatly contributed to this project.
