# Sleep Disorder Analysis Dashboard — Project Report

## 1. Executive Summary

The Sleep Disorder Analysis Dashboard is an interactive Power BI project that explores a synthetic dataset of 469 records. It compares records labelled Insomnia and Sleep Apnea across sleep duration, a project-defined weighted Sleep Score, sleep quality, stress, BMI category, occupation, daily steps, age, and gender. The dashboard is intended to demonstrate healthcare data analysis and data storytelling skills, not to provide clinical evidence.

## 2. Business Problem and Objectives

Business problem: How can a compact interactive report help a viewer explore differences between records labelled Insomnia and Sleep Apnea across selected sleep and lifestyle measures?

Objectives:
• Summarize the two recorded disorder groups and their shares of the dataset.
• Compare average sleep duration and the dashboard's weighted Sleep Score.
• Explore sleep-quality and stress values across age.
• Compare BMI-category counts and average daily steps by occupation.
• Enable gender-based exploration of the measures.

## 3. Business Questions

1. How many records are labelled Insomnia and Sleep Apnea, and what percentage of all records does each represent?
2. How do average sleep duration and the dashboard's weighted Sleep Score compare between the groups?
3. How do sleep quality and stress values vary across age in the displayed groups?
4. How are BMI categories distributed within each disorder group?
5. How does average daily step count vary by occupation within each group?
6. How can the measures be explored by gender?

## 4. Dataset and Methodology

Source: SleepDisorder_Dataset.csv. The supplied dataset contains 469 records and 10 columns, with one unique Person ID per record. Fields include gender, age, occupation, sleep duration, quality of sleep, stress level, BMI category, daily steps, and sleep-disorder status.

Power Query evidence supplied for this project shows the Source, Promoted Headers, and Changed Type steps. Do not claim additional cleaning or duplicate removal unless those steps were actually performed. The disorder field contains 97 Insomnia records, 76 Sleep Apnea records, and 296 blank records. Blank is described as “no recorded disorder,” while noting that the source does not establish whether blank means no disorder or not assessed.

The report uses Power BI visuals and DAX measures. The weighted Sleep Score combines sleep quality (40%), sleep duration (40%), and inverse stress level (20%). It is a project-defined metric rather than a validated clinical scale.

## 5. Key Metrics

• Insomnia: 97 records, 20.68% of all records; average sleep duration 7.14 hours; displayed weighted Sleep Score 67.93.
• Sleep Apnea: 76 records, 16.20% of all records; average sleep duration 6.36 hours; displayed weighted Sleep Score 60.88.
• Overall recorded disorder status: 173 of 469 records, or 36.89%, have a nonblank Sleep Disorder value.
• Among the 173 records with a recorded disorder, 56.07% are labelled Insomnia and 43.93% Sleep Apnea.

The Sleep Score values were independently reproduced from the CSV using the dashboard's DAX formula (67.9268 and 60.8829 before rounding).

## 6. Key Insights and Observations

1. 173 of 469 records (36.89%) have a nonblank disorder value.
2. Average sleep duration is 7.14 hours for Insomnia and 6.36 hours for Sleep Apnea. The blank-disorder group averages 7.64 hours in the source-data verification.
3. Average Quality of Sleep on the dataset's 1–10 field is 5.78 for Insomnia, 5.21 for Sleep Apnea, and 6.05 for blank-disorder records. This field is not the same as the dashboard's weighted Sleep Score.
4. The overall Pearson correlation between stress and quality of sleep was approximately -0.021, essentially no linear association in this dataset. Do not claim stress causes lower sleep quality.
5. 28 of 76 Sleep Apnea records (36.84%) are in the Obese BMI category, compared with 27.72% of all records. This is descriptive, not causal.
6. Mean daily steps were approximately 7,225 for Sleep Apnea, 9,805 for Insomnia, and 10,608 for blank-disorder records. Occupational subgroup sizes are small and require caution.

## 7. Recommendations

• Improve chart titles and add a legend to identify each line in the age chart.
• Fully display labels such as Female and Underweight.
• Keep the “Sleep Disorder Status %” label on the 36.89% KPI and confirm its slicer behavior.
• Keep the corrected “Sleep Apnea Case Count” label.
• Review six pairs of records that match in every field except Person ID; document the decision rather than removing rows automatically.
• Document that the Sleep Score is average-based and that its duration term (divided by 8) is uncapped.
• Consider including a clearly labelled no-recorded-disorder comparison group and showing sample sizes.
• Treat the findings as exploratory and avoid clinical or causal claims.

## 8. Limitations and Disclaimer

This is a synthetic dataset, not a real-patient dataset or a source of clinical evidence. The meaning of blank Sleep Disorder cells is not confirmed. Six duplicate-content pairs have been identified for review. The Sleep Score is a custom composite measure and its displayed values were independently reproduced from the CSV, but it is average-based and its duration term is uncapped. No significance tests were performed. The dashboard must not be used for diagnosis, treatment decisions, or claims of causation.

## 9. Future Improvements

1. Consider capping the duration component and documenting the score design.
2. Confirm how the 36.89% measure responds to gender filtering.
3. Add line-chart legends and use age-based titles accurately.
4. Review duplicate-content rows.
5. Improve sample-size and denominator labelling.
6. Consider adding the blank-disorder group as a comparison baseline, with the limitation that blank does not necessarily mean confirmed absence of a disorder.

