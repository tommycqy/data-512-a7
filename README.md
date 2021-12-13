# data-512-a7
*README file for 512hw7*
---

### Introduction <br>
In this analysis, I plan to explore how the Covid-19 pandemic and the mask mandate impacted the job market (unemployment rate) of Maricopa County, Arizona. I also want to see how another county with a similar population - Cook County in Illinois, is doing compared to Maricopa County. (Maricopa, AZ has a population of 4.485 million while Cook, IL has a population of 5.15 million.) Furthermore, I want to compare the situation in Maricopa County and that in the whole Arizona State.

It comes down to the three following research questions.
- Research Question #1
  - What does the pandemic situation look like in Maricopa County vs Cook County? (Infection rate, daily cases) What about the estimated mask prevalence in those counties?
  - Hypothesis: Maricopa County has a higher infection rate and significantly more cases than Cook County. The estimated mask prevalence in Maricopa County is lower than that in Cook County.
- Research Question #2
  - How was the unemployment rate in Maricopa County affected by the pandemic? What about Cook County?
  - Hypothesis: Every 10% increase in infection rate would result in a 1% increase in unemployment in Maricopa County, Arizona. The number would be lower for Cook County, Illinois.
- Research Question #3
  - One of the major metropolitan areas - Phoenix, is in Maricopa County, Arizona. What does the infection rate look like in Maricopa County compared to the rest of Arizona? What about the unemployment rate? Which area’s unemployment rate is more sensitive to the pandemic?
  - Hypothesis: The infection rate is lower in Maricopa County compared to the rest of Arizona State. The unemployment rate is lower in Maricopa County compared to that of Arizona State. The unemployment rate in Maricopa County is less sensitive to the pandemic.


### Data Source and Information <br>
There are three initial data files downloaded in csv format:<br>
- The New York Times mask compliance survey data. (https://github.com/nytimes/covid-19-data/tree/master/mask-use)
  - License: Copyright 2021 by The New York Times Company
  - All columns are used in this project
    - COUNTYFP - the FIPS code
    - All columns representing the frequency of mask wearing
- The RAW_us_confirmed_cases.csv file from the Kaggle repository of John Hopkins University COVID-19 data.(https://www.kaggle.com/antgoldbloom/covid19-data-from-john-hopkins-university?select=RAW_us_confirmed_cases.csv)
  - License: Attribution 4.0 International (CC BY 4.0)
  - Three columns in this data are used in this project
    - 'FIPS' - the FIPS code 
    - All the date columns recording the raw confirmed cases are used
- The CDC dataset of masking mandates by county. (https://www.google.com/url?q=https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i&sa=D&source=docs&ust=1636073389074000&usg=AOvVaw2UizNDNMnoGaGs9Qj9TgO0)
  - Licesnse: Public Use (User Agreement: https://www.cdc.gov/nchs/data_access/restrictions.htm)
  - Three columns in this data are used in this project
    - 'Date'
    - 'Order Code' - unclear waht it means
    - 'FIPS' - the FIPS code 
    - 'Face_Masks_Required_in_Public' - whether face mask is mandated

- The unemployment rate by month dataset in Maricopa County & Cook County from the Federal Reserve Bank of St. Louis. (https://fred.stlouisfed.org/series/AZMARI3URN) (https://fred.stlouisfed.org/series/ILCOOK1URN)
    - MaricopaFED.csv
    - CookFED.csv
    - Licesnse: Public Use (User Agreement: https://www.bls.gov/developers/termsOfService.htm) (This data is originally from BLS)
    - One column in this data are used in this project
      - 'Unemployment' - the monthly unemployment rate

- The unemployment rate by month dataset in Arizona State from the Bureau of Labor Statistics. (https://www.bls.gov/eag/eag.az.htm)
    - ArizonaBLS.csv 
    - One column in this data are used in this project
    - Licesnse: Public Use (User Agreement: https://www.bls.gov/developers/termsOfService.htm) (This data is originally from BLS)
      - 'unemployment_rate' - the monthly unemployment rate

- There are also two intermediate dataframes worth mentioning. They are called 'maricopa_cases_df_reduced' and 'cook_cases_df_reduced'. These two were resulted from cleaning and combining the above datasets.
    - The columns of those two datasets are
      - Province_State
      - FIPS - the FIPS code of state and county
      - date
      - case_count - culmulative Covid-19 case count
      - order_code
      - daily_new_cases - daily new Covid-19 case count
      - daily_infection_rate - daily new Covid-19 case count / population of that county
      - new_cases_7_day_moving_average - 7-day moving average of daily new cases
