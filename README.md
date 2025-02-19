## VisaPredictor: Predictive Modeling for Optimized Visa Processing

### Context:
Business communities in the United States are facing high demand for human resources, but one of the constant challenges is identifying and attracting the right talent, which is perhaps the most important element in remaining competitive. Companies in the United States look for hard-working, talented, and qualified individuals both locally as well as abroad.

The Immigration and Nationality Act (INA) of the US permits foreign workers to come to the United States to work on either a temporary or permanent basis. The act also protects US workers against adverse impacts on their wages or working conditions by ensuring US employers' compliance with statutory requirements when they hire foreign workers to fill workforce shortages. The immigration programs are administered by the Office of Foreign Labor Certification (OFLC).

OFLC processes job certification applications for employers seeking to bring foreign workers into the United States and grants certifications in those cases where employers can demonstrate that there are not sufficient US workers available to perform the work at wages that meet or exceed the wage paid for the occupation in the area of intended employment.

### Objective:
In FY 2016, the OFLC processed 775,979 employer applications for 1,699,957 positions for temporary and permanent labor certifications. This was a nine percent increase in the overall number of processed applications from the previous year. The process of reviewing every case is becoming a tedious task as the number of applicants is increasing every year.

The increasing number of applicants every year calls for a Machine Learning based solution that can help in shortlisting the candidates having higher chances of VISA approval. This project uses a classification-based Machine Learning solution to predict the likelihood of VISA approval for applicants based on their profile attributes. It aims to streamline the approval process by identifying key factors influencing case outcomes.

### Data Description
The data contains the different attributes of the employee and the employer. The detailed data dictionary is given below.

- case_id: ID of each visa application
- continent: Information of continent of the employee
- education_of_employee: Information of education of the employee
- has_job_experience: Does the employee has any job experience? Y= Yes; N = No
- requires_job_training: Does the employee require any job training? Y = Yes; N = No
- no_of_employees: Number of employees in the employer's company
- yr_of_estab: Year in which the employer's company was established
- region_of_employment: Information of foreign worker's intended region of employment in the US.
- prevailing_wage: Average wage paid to similarly employed workers in a specific occupation in the area of intended employment. The purpose of the prevailing wage is to ensure that the foreign worker is not underpaid compared to other workers offering the same or similar service in the same area of employment.
- unit_of_wage: Unit of prevailing wage. Values include Hourly, Weekly, Monthly, and Yearly.
- full_time_position: Is the position of work full-time? Y = Full Time Position; N = Part Time Position
- case_status: Flag indicating if the Visa was certified or denied

### Dataset Highlights:
- **Total Applications Analyzed**: 25,480
- **Columns/Attributes**: 12, including `education_of_employee`, `has_job_experience`, `requires_job_training`, `prevailing_wage`, `region_of_employment`, and `case_status` (target variable)
- **Target Class Distribution**: 
  - Certified: 66.8%
  - Denied: 33.2%

### Features Impacting VISA Approval:
- **Education Level**: Higher education (Master's, Doctorate) correlates positively with approval.
- **Job Experience**: Applicants with prior job experience (`Y`) show higher approval rates.
- **Prevailing Wage**: Higher wages offered increase the likelihood of visa certification.
- **Region of Employment**: Employment regions also play a role in approval rates.

### Machine Learning Models Used:
Several models were built and tuned to optimize predictive performance. Below are key metrics of the best-performing models:

| **Model**                | **Accuracy** | **Precision** | **Recall** | **F1 Score** |
|--------------------------|--------------|---------------|------------|--------------|
| **Random Forest**        | 74.6%        | 82.9%         | 77.9%      | 80.4%        |
| **Gradient Boost (Tuned)** | 75.5%        | 78.3%         | 87.6%      | 82.7%        |
| **XGBoost (Tuned)**      | 80.6%        | 81.9%         | 90.9%      | 86.2%        |
| **Stacking Classifier**  | 75.0%        | 76.8%         | 89.6%      | 82.7%        |

### Best Model:
- **XGBoost (Tuned)** achieved superior performance:
  - Accuracy: **80.6%**
  - F1 Score: **86.2%**
  - Provides the best combination of precision and recall for identifying certified applicants.

### Conclusion:
The analysis identified key factors influencing visa certifications. The XGBoost model offers reliable predictions to assist in shortlisting applications with high approval potential. The project demonstrates how data-driven solutions can improve the visa processing pipeline's efficiency.

---
