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
**Correlation Analysis between Age and Billing amount:**

<img width="998" height="645" alt="image" src="https://github.com/user-attachments/assets/6a65dd87-cb06-49b5-a54a-906df6fb0c36" />

- - 1. **Medication/Medicine Analysis worksheet**

**Columns:**

- Name
- Condition
- Medication
- Billing amount

From the below pivot table we can deduce the following insights about the medications:

**For Arthritis** 🡪 most prescribed: Aspirin ; Least prescribed: Ibuprofen

**For Asthma** 🡪most prescribed: Paracetamol ; Least prescribed: Aspirin

**For Cancer** 🡪most prescribed: Lipitor ; Least prescribed: Aspirin

**For Diabetes** 🡪most prescribed: Lipitor ; Least prescribed: Paracetamol

**For Hypertension**🡪most prescribed: Ibuprofen ; Least prescribed: Penicillin

**For Obesity** 🡪most prescribed: Penicillin ; Least prescribed: Paracetamol

<img width="982" height="286" alt="image" src="https://github.com/user-attachments/assets/5fde3c06-9545-4456-a954-2e76c62c4467" />

From the pivot table given below we have a lot of interesting findings :

We can not derive any meaning from the results that are Inconclusive. We need to highlight the medications which are the least in ABNORMAL and the most in NORMAL.  
In this sense, a medical condition sequentially gives us certain findings .

For

- Arthritis ; Lipitor is the best medicine according to test results
- Asthma; Ibuprofen
- Cancer ; Lipitor
- Diabetes; Penicillin
- Hypertension; Ibuprofen
- Obesity ; Aspirin
But above data has a lot of conflicts that suggests that a lot of doctors also prescribe medications that are not optimized for the best test results. Only for cancer and hypertension, have the doctors prescribed Lipitor and Ibuprofen respectively which is also fits for best test results.

<img width="532" height="647" alt="image" src="https://github.com/user-attachments/assets/4c4284a9-53f3-48c6-ab16-431dc32c8293" />
From the table below we can infer that all the medications have almost the same amount of average billing amount hence one medication is not more or less expensive than another.

Ibuprofen costs slightly more than other medications.

<img width="476" height="202" alt="image" src="https://github.com/user-attachments/assets/e315d386-1cb0-4fa9-b20a-0bbb9866769a" />

- - 1. **Medical Condition Analysis worksheet**

**Columns:**

- Name
- Days Admitted
- Condition
- Billing amount
- Gender
- Blood Type

<img width="524" height="198" alt="image" src="https://github.com/user-attachments/assets/705fce59-368c-4ea0-82fe-90aa9d26581b" />
This table shows less about the population insights and more about this particular dataset because it shows that the digits are more or less evenly spread when it comes to relation with the medical condition, not necessarily showing true facts.

Given below is the pivot table that aims to display the distribution of medical condition in Male vs Female:
<img width="426" height="301" alt="image" src="https://github.com/user-attachments/assets/cea4f316-87f7-49f5-af4e-8348ff375499" />

On general inspection of this data, we can derive that similar to the previous insight that we found this data is also more or less distributed equally among the attributes and gender does not affect the probability of having a certain medical condition.

However, we can look at the maximum and minimum values :

- Females having arthritis is the most common in the dataset .
- Females having Asthma is the least common.

Below is the pivot table which attempts to relate blood type with condition.

Non-interestingly enough, medical conditions are also evenly distributed across all the types of blood.

- A+ having Diabetes is the most common.
- B+ having Hypertension is the least common.

  <img width="829" height="284" alt="image" src="https://github.com/user-attachments/assets/565f2d31-48dc-46de-997f-956085cb985d" />

  - - 1. **Bill Analysis worksheet**

**Columns:**

- Name
- Test Results
- Billing amount
- Insurance provider

Bill can be analysed in the following key ways:

- Which insurance company gave what amount of insurance in the form of a pivot table.

The pivot table of insurance provider and the sum of billing amount displays that all the insurance companies paid almost the same amount of insurance and have similar bill average which means there are very less outliers in the data.

<img width="648" height="201" alt="image" src="https://github.com/user-attachments/assets/157bf280-71d1-4742-8f24-a4185a359592" />
- Pie chart that can display which company gave how much of insurance as a fraction of the whole amount. The pie chart clearly shows that out of the total amount which is 1.4B \$ all 5 of the companies have 1/5 share each of the amount of insurance paid.
- A pivot table of Test result and Average of billing amount which can show if amount of money spend can increase your chances of a normal test result. The last pivot table shows that Test results can't be necessarily related with the billing amount because almost equal amount of money was paid which resulted in three different test results.
<img width="489" height="352" alt="image" src="https://github.com/user-attachments/assets/5d53db58-2f91-4690-8660-e8066cbb1d6e" />

<img width="512" height="153" alt="image" src="https://github.com/user-attachments/assets/8bba133a-5c02-4bbb-b314-52d6d0e39f8b" />

- - 1. **Conclusion**

By conducting the above study of different attributes, we can conclude that the data was equally distributed amongst all the attributes and no solid conclusions can be drawn because the data is not skewed towards any particular outcome favouring or unfavouring the results. This study told us the methods by which we can conduct studies on similar datasets which need to be cleaned, processed and ultimately explored to find interesting insights about the population behaviour in the data represented in the form of a sample.

This framework can be subsequently used to create a dashboard representing different stats on one single page.













