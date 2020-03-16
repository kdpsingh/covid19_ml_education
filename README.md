# COVID-19 Machine Learning Dataset
## Intended For Educational Use Only

The dataset is located at [covid_ml.csv](https://github.com/ml4lhs/covid19_ml_education/raw/master/covid_ml.csv).

"It’s hard to over value the importance of really caring about the outcome when learning modeling." - JD Long

The COVID-19 pandemic has affected the lives of many people around the world and is a growing threat to our health as the case volume continues to rise in the United States. 

The original data comes from the following source: http://virological.org/t/epidemiological-data-from-the-ncov-2019-outbreak-early-descriptions-from-publicly-available-data/337

The original dataset is based on public reports of COVID-19 cases reported internationally. There is a source column that provides a link to the website (or news source) where the case was found.

At the original source, there is a Google Sheet that contains live updating data. The Google Sheet receives very high traffic (blocking access to users), so the data was first exported as an Excel file on March 14 at 5:30 pm. This dataset will be out-of-date by the time you read this as the number of cases is growing exponentially.

From the original dataset, the covid19_ml.csv dataset contains those cases for which:
- a date of onset is provided
- a date of admission is either missing or occurs *after* the date of onset

This set of inclusion criteria reduces the number of cases from 20,758 to 861. The purpose of this dataset (intended for education) is to predict the urgency with which a COVID-19 patient will need to be admitted to the hospital from the time of onset of symptoms.

*Primary predictors:* age, sex, cough, fever, chills, sore_throat, headache, fatigue

*Outcomes (for teaching purposes):*
- Classification: urgency_of_admission (binary: 0-1 days to admission => High, 2+ days or no admission => Low)
- Regression: days_onset_to_admission (numeric)

*Optional predictors:*
- Use NLP to extract additional predictors from the symptoms column
- country, province, city (useful for teaching about high-cardinality data)
- latitude and longitude
