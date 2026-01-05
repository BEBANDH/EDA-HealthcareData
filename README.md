# EDA-HealthcareData
Healthcare dataset 
Dummy data with Multi Category Classification Problem
Extracted from: https://www.kaggle.com/datasets/prasad22/healthcare-dataset/data


**Dataset Information:**

Each column provides specific information about the patient, their admission, and the healthcare services provided, making this dataset suitable for various data analysis and modeling tasks in the healthcare domain. Here's a brief explanation of each column in the dataset :

- **Name:** This column represents the name of the patient associated with the healthcare record.
- **Age:** The age of the patient at the time of admission, expressed in years.
- **Gender:** Indicates the gender of the patient, either "Male" or "Female."
- **Blood Type:** The patient's blood type, which can be one of the common blood types (e.g., "A+", "O-", etc.).
- **Medical Condition:** This column specifies the primary medical condition or diagnosis associated with the patient, such as "Diabetes," "Hypertension," "Asthma," and more.
- **Date of Admission:** The date on which the patient was admitted to the healthcare facility.
- **Doctor:** The name of the doctor responsible for the patient's care during their admission.
- **Hospital:** Identifies the healthcare facility or hospital where the patient was admitted.
- **Insurance Provider:** This column indicates the patient's insurance provider, which can be one of several options, including "Aetna," "Blue Cross," "Cigna," "UnitedHealthcare," and "Medicare."
- **Billing Amount:** The amount of money billed for the patient's healthcare services during their admission. This is expressed as a floating-point number.
- **Room Number:** The room number where the patient was accommodated during their admission.
- **Admission Type:** Specifies the type of admission, which can be "Emergency," "Elective," or "Urgent," reflecting the circumstances of the admission.
- **Discharge Date:** The date on which the patient was discharged from the healthcare facility, based on the admission date and a random number of days within a realistic range.
- **Medication:** Identifies a medication prescribed or administered to the patient during their admission. Examples include "Aspirin," "Ibuprofen," "Penicillin," "Paracetamol," and "Lipitor."
- **Test Results:** Describes the results of a medical test conducted during the patient's admission. Possible values include "Normal", "Abnormal", or "Inconclusive", indicating the outcome of the test.

**Potential correlation candidates:**

Correlation can only be calculated for numerical data

- Age 🡪 Condition; Age 🡪Billing amount
- Medication 🡪 Condition; Medication 🡪 Billing amount; Medication 🡪 Test Results
- Condition 🡪 Billing amount; Condition 🡪 Days Admitted, Condition 🡪 Gender, Blood type 🡪 Condition
- Test Results 🡪 Billing amount; (Does more money really amount to successful treatment?)

**Sorting candidate column:** AGE or DAYS ADMITTED

**Note:** Date table: Annually, Quarterly, Monthly, Weekly

**General stats:**  

- Insurance provided by an insurance company according to date table
- Cases of each Condition according to date table
- Increase in medical conditions with age
- Average billing amount (Different b/w median and mean)
- Total amount spent in healthcare sector
- Average Days Admitted according to the condition
- Number of Cases according to the blood group

**  
Data Cleaning Steps**

- Convert csv to xlsx

**Initial formatting:**

- heading colours,
- align centred the entries
- fixes in the name column
  - Convert names to proper lowercase
  - Removing honorifics (Dr Mr Mrs)
  - Removing dot special character from name
  - Convert the name into proper name with first letter uppercase
- Creating a S.no column,
- Convert billing amount to number, shorten to 2 decimal places
- Basic fixes in the table structure
- Remove special characters in hospital name
- Create a Days Admitted column
- Sort the data according to age
- Convert Male to M and Female to F

**Data Processing**

- - 1. **Age Analysis worksheet**

Create an extra Age to Condition worksheet with the following data outcomes

**columns:**

- name
- age
- condition
- Billing amount

- Extract a list of unique medical conditions from the CONDITION column.
- Count the total number of people in one condition.
- Make a pivot table with Age in rows and CONDITION in columns, Put Count of Age in values show as percentage.
- Group Age according to class interval size 10.
- Correct the formatting and colours of the pivot table.
- Add the conditional formatting in the pivot table as heat map.
- More details to be added in the form of charts.

**Insights Found in this sheet:**

By the below data we can clearly deduce that in this dataset:

- most of the people having a Medical Condition fall in the ranges from 35 to 67 and furthermore most of the people in this range are suffering from Obesity and Diabetes.
- According to the heatmap, second range of people lie in the 68-78 range for Arthritis and in the 57 - 67 range for Hypertension.
- We can also derive that young aged people do have the least number of medical conditions.
- People in the range of age 79-89 are not suffering in less numbers, but the number of these people is small in this dataset to begin with.
- From the perspective of relation between Age and Medical conditions this data closely mimics real world population as observed.
- When trying to find a correlation between Age and Billing amount the score is -0.003832 which is almost no correlation, which clearly suggests that in this data Age does not affect Billing amount in any way.

  <img width="998" height="645" alt="WINWORD_EH4eDaLE3r" src="https://github.com/user-attachments/assets/8f7f437c-aaae-47e4-ac9f-a8c78120f516" />


