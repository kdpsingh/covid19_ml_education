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

*Primary predictors:*
- age (if an age range was provided in the source data, only the first number is used)
- sex
- cough, fever, chills, sore_throat, headache, fatigue (all derived from the symptoms column using regular expressions)

*Outcomes (for teaching purposes):*
- Classification: urgency_of_admission
  - 0-1 days from onset of symptoms to admission => High
  - 2+ days from onset of symptoms to admission *or* no admission => Low
- Regression: days_onset_to_admission (numeric)

*Optional predictors:*
- Use NLP to extract additional predictors from the symptoms column
- country, province, city (useful for teaching about high-cardinality data)
- latitude and longitude

## Should this data be used for research?

No. Students working with this dataset should understand that both the source data and the ML data have several limitations:
- The source data is crowdsourced and may contain inaccuracies.
- The source data has a lot of missing information. This should be evident from the fact that nearly 20,000 of the cases were excluded due to missingness of information related to the outcome variable when creating the ML dataset.
- There may be duplicate patients in this dataset
- There is a substantial amount of missingness in the symptoms data.
- The data contains some patients who are missing a date of confirmation. The status of these patients is a bit unclear.

**And most importantly:**
- The entire premise is flawed. The fact that a patient was admitted the same day as experiencing symptoms may have more to do with the availability of hospital beds as opposed to the patient's acuity of illness.
- Also, the fact that less sick patients or asymptomatic patients may not have been captured in the source dataset mean that the probabilities estimated by any model fit on this data are unlikely to reflect reality.

**Educating students about the limitations of both the data and the machine learning task should be part of the course content.**
