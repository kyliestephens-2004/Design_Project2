# DS 4320 Project 2: Factors Influencing Loan Default Risk 

Executive Summary - Short paragraph explaining the
contents of the respository in executive form

Name: Kylie Stephens

NetID: uqj5uw

DOI - create a DOI for your project 
 

Press Release: 

https://github.com/kyliestephens-2004/Design_Project2/blob/main/Press-Release.md
  

Pipeline - link to pipeline file 
 

License State- MIT License

https://github.com/kyliestephens-2004/Design_Project2/blob/main/LICENSE

## Problem Definition 

General Problem: Understanding factors that influence loan default risk.

Refined Problem: Identifying which borrower financial attributes (income, debt-to-income ratio, credit score, etc.) most strongly predict loan default behavior.

**Project Motivation**

A major goal of companies with financial loan services is to decrease the number of defaults on loan payments, ensuring that all payments are being completed on time. Loan defaults create significant financial risk for lenders and impact credit availability in the broader economy. Improving prediction accuracy can help reduce losses and support better lending decisions. In the financial industry, this is a very relevant machine learning problem, and improved prediction accuracy benefits both companies and borrowers.   

**Rationale for Problem Refinement**

While the general problem vaguely acknowledges the known fact that defaults on loan payments occur, the refined problem hones in on a specific way to attempt to solve this problem, or at least reduce the number of defaults on loan payments. Narrowing the problem to specific borrower-level features allows for more precise modeling and actionable insights that can be directly used in lending decisions. Looking into feature importance in machine learning provides comprehensible insights and transparency into why the model is coming to a decision regarding an individual's risk score. It also provides more specific places to focus in on for both borrowers and lenders in the loan process; for example, a borrower may be given a risk score of .8 for defaulting, and the model could be used to generate a report, showing the lender and borrower that this individual is at high risk of defaulting because of credit score and income. It also could debunk lenders' prior beliefs regarding what factors most heavily influence loan default risk, allowing them to see the process from a more objective view (even though data itself may contain biases, the human bias in deciding what factors are most influential is eliminated).

**Press Release Snippet**

Headline of Press Release: Loan Default Risk Is Driven Primarily by Debt Burden and Credit Quality

Click https://github.com/kyliestephens-2004/Design_Project2/blob/main/Press-Release.md to read the press release.

## Domain Exposition

**Terminology**

| Term | Definition |
|------|------------|
| Loan ID | Unique identifier for each loan application |
| Applicant Age | Age of the loan applicant (years) |
| Income | Annual income of the applicant |
| Education | Highest education level completed |
| Employment Type | Type of employment (e.g., full-time, part-time, self-employed) |
| Months Employed | Number of months the applicant has been employed |
| Marital Status | Applicant’s marital status |
| Dependents | Whether the applicant has dependents (True/False) |
| Credit Score | Numerical score representing creditworthiness |
| Number of Credit Lines | Total active credit accounts held by applicant |
| Mortgage Status | Whether the applicant has a mortgage (True/False) |
| Co-signer Status | Whether the loan has a co-signer (True/False) |
| Loan Amount | Total amount borrowed |
| Loan Term | Duration of loan in months |
| Interest Rate | Interest rate applied to the loan |
| Loan Purpose | Reason for loan (e.g., education, medical, personal) |
| Debt-to-Income Ratio (DTI) | Ratio of debt payments to income |
| Default | Loan outcome (1 = default, 0 = no default) |



**Project Domain**

The domain of this project is financial risk analytics, specifically loan default prediction in consumer lending. This area focuses on using borrower financial and demographic information to assess the likelihood that an individual will fail to repay a loan. Key factors in this domain include credit scores, income, debt-to-income ratios, employment history, and loan characteristics such as interest rate and term length. Financial institutions use this type of analysis to make lending decisions, manage risk exposure, and set interest rates appropriately. In this project, loan-level data is structured using a document-based model to reflect how borrower attributes and loan outcomes are naturally grouped, allowing for more efficient analysis of default patterns across different segments of the lending population. The key factors included in the dataset and terminology table above will provide insight into individual behaviors that help a financial institution determine if said individual should be approved for a loan or if they should denied.

**Background Readings:**

https://myuva-my.sharepoint.com/:f:/g/personal/uqj5uw_virginia_edu/IgCp68q99BWNRbeH3FqCeSZ4AcBZOXcLsy3ktU2TxGQe7Uk?e=Qtr2oL

| Title | Brief Description | Link |
|------|------------------|------|
| Loan Default Risk and Macroeconomic Conditions (Albanesi & Domos) | Academic paper analyzing how macroeconomic conditions and borrower characteristics influence default risk. | https://myuva-my.sharepoint.com/:b:/g/personal/uqj5uw_virginia_edu/IQCo9buHkDvSQYjoa3wsGzE8ASH_35FAU4j0upuPolAtVz8?e=uVec1U |
| Default Rate (Investopedia) | Explains what loan default rate means, how it is calculated, and why it is important in credit risk analysis. | https://myuva-my.sharepoint.com/:b:/g/personal/uqj5uw_virginia_edu/IQAv1OOzCuyfToaM85pBJjW1AZiYsnTIeRRWX0AJpmOytkg?e=1550Ik |
| Consumer Delinquency Trends (Federal Reserve) | Reports recent trends in consumer delinquency and repayment behavior in the U.S. credit system. | https://myuva-my.sharepoint.com/:b:/g/personal/uqj5uw_virginia_edu/IQA5jsZcnnuoRI-Mnorm8F0gAfyZ2Hz639gzTCHwe3nfIxw?e=dLvXc4 |
| Predicting Loan Default Risk Using Machine Learning (Medium) | Demonstrates a practical machine learning pipeline for predicting loan default using borrower features. | https://myuva-my.sharepoint.com/:b:/g/personal/uqj5uw_virginia_edu/IQAcV45ZLwdsTZ4DqZFUiWEdAZ2K9zafzOq60JZw5ypt9RM?e=imsToA |
| Machine Learning Approaches to Credit Risk (ScienceDirect) | Research article exploring advanced ML techniques for credit risk prediction and model performance. | https://myuva-my.sharepoint.com/:b:/g/personal/uqj5uw_virginia_edu/IQBRSRr4DKy2Q4yEHPHUbNhLAZ5VD0NbMyXWSV5xN1AC-JM?e=ZhsmeA |

## Data Creation


**Acquisition and Provenance**


**Code Table**

| File / Script         | Description                                                                                                                                                                                                                                  | Link to Code                                                                            |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `DataCreation_P2.ipynb` | Loads raw Loan_default.csv downloaded from kaggle. Converts this to a document model form with implicit schema. Connects to MongoDB and uploads documents into database. Data ingestion, MongoDB setup, import, and schema transformation are done using mongosh. | [GitHub link] https://github.com/kyliestephens-2004/Design_Project2/blob/main/DataCreation_P2.ipynb |


**Link to Code for Data Assembly:**

https://github.com/kyliestephens-2004/Design_Project2/blob/main/DataCreation_P2.ipynb

**Rationale**

A major judgment call involved deciding whether to preserve the original flat schema or restructure the documents into a nested format. While the CSV was naturally tabular, a nested MongoDB schema was preferred because it better reflects real-world borrower relationships and improves interpretability for machine learning. For example, grouping age, income, and education under applicant makes the data easier to reason about than maintaining many disconnected flat columns. Another important decision was converting categorical “Yes/No” variables (such as mortgage ownership and co-signer presence) into Boolean values. This reduces ambiguity, improves consistency, and simplifies feature engineering later in the modeling process. Uncertainty may be introduced during type conversion (for example, converting numeric values stored as strings) or during reshaping if field mappings are incorrectly specified. To mitigate this, document counts were verified after import, and sample records were inspected using findOne() and countDocuments() to ensure structural consistency.
 
**Bias Identification**

Bias could be introduced in the dataset during the original data collection process on Coursera/Kaggle because the data may not represent the full population of loan applicants. If the dataset was collected from a specific institution, platform, or region, it may reflect selection bias, where certain types of borrowers are overrepresented while others are underrepresented or excluded. Historical lending data can also contain societal and institutional biases, such as unequal loan approval patterns based on income, credit history, or demographic factors. These biases become embedded in the dataset and can influence any downstream analysis. Downstream effects of these biases include wealth inequality and disparities may be reflected in incomes and credit scores, even though they are a product of prior systemic discrimination and inequalities in society. This ties back to the idea that data can never be neutral.
 

**Bias Mitigation**

Bias can be addressed in analysis by first identifying whether certain groups or outcomes are over- or under-represented in the dataset. Techniques such as re-sampling, re-weighting, or stratified analysis can help reduce imbalance across groups if demographic variables are available. Model evaluation should include fairness-aware metrics to assess whether predictions differ systematically across groups. However, since this dataset may not include all relevant protected attributes, bias cannot be fully removed and should instead be acknowledged as a limitation, especially because bias stemming from data collection is most likely the dominating form of bias in this dataset. Also, other features not included in this dataset would be needed to understand if a representative sample was collected (i.e. race).

## Metadata

**Implicit Schema Guidelines**

The database is organized so that related information is grouped together inside each document. Instead of keeping every field in one long flat list, the data is stored in smaller sections that make it easier to read and analyze.
Each document represents one borrower and their loan information. The document is divided into four main sections: 
- applicant → personal and employment information like age, income, education, marital status, and whether they have dependents
- credit_profile → financial and credit details like credit score, number of credit lines, mortgage status, and whether they have a co-signer
- loan → loan-specific details like loan amount, loan term, interest rate, purpose of the loan, and debt-to-income ratio
- outcome → whether the borrower defaulted on the loan or not
There is also a loan_id field that acts as a unique identifier for each borrower.
Fields like “Yes” and “No” were changed into true and false values so the data would be easier to work with in machine learning models. Number fields were also kept as integers or decimals depending on the type of value.

This is an image of one of the documents in the database - you can see the structure, nesting, and field names. This displays the implicit schema in MongoDB.
### INSERT IMAGE

**Data Summary**

| Attribute            | Summary                                                                                  |
| -------------------- | ---------------------------------------------------------------------------------------- |
| Database Name        | `mydb`                                                                                   |
| Raw Collection       | `loan_default`                                                                           |
| Processed Collection | `loan_default_nested`                                                                    |
| Total Documents      | 255347 documents in each collection.                                                    |
| Raw Structure        | Flat JSON documents imported from CSV.                                                    |
| Processed Structure  | Nested JSON documents grouped into applicant, credit profile, loan, and outcome sections. |
| Target Variable      | `Default` (raw) / `outcome.default` (nested)                                             |
| Primary Identifier   | `LoanID` (raw) / `loan_id` (nested)                                                      |
| Missing Values       | No missing values.                                                                        |
| Source               | Kaggle/Coursera Loan Default Prediction Dataset                                                   |


**Data Dictionary**

| Column Name       | Column Type | Data Type | Description                                                                 | Example                  |
|------------------|------------|----------|-----------------------------------------------------------------------------|--------------------------|
| LoanID          | Identifier | string   | A unique identifier for each loan.                                          | L00012345               |
| Age             | Feature    | integer  | The age of the borrower.                                                    | 35                       |
| Income          | Feature    | integer  | The annual income of the borrower.                                          | 75000                    |
| LoanAmount      | Feature    | integer  | The amount of money being borrowed.                                         | 20000                    |
| CreditScore     | Feature    | integer  | The credit score of the borrower, indicating creditworthiness.              | 720                      |
| MonthsEmployed  | Feature    | integer  | Number of months the borrower has been employed.                            | 60                       |
| NumCreditLines  | Feature    | integer  | Number of credit lines the borrower has open.                               | 5                        |
| InterestRate    | Feature    | float    | The interest rate for the loan.                                             | 5.75                     |
| LoanTerm        | Feature    | integer  | The term length of the loan in months.                                      | 36                       |
| DTIRatio        | Feature    | float    | Debt-to-Income ratio (debt compared to income).                             | 0.32                     |
| Education       | Feature    | string   | Highest level of education attained.                                        | Bachelor's               |
| EmploymentType  | Feature    | string   | Employment status of the borrower.                                          | Full-time                |
| MaritalStatus   | Feature    | string   | Marital status of the borrower.                                             | Single                   |
| HasMortgage     | Feature    | string   | Whether the borrower has a mortgage.                                        | Yes                      |
| HasDependents   | Feature    | string   | Whether the borrower has dependents.                                        | No                       |
| LoanPurpose     | Feature    | string   | Purpose of the loan.                                                        | Auto                     |
| HasCoSigner     | Feature    | string   | Whether the loan has a co-signer.                                           | Yes                      |
| Default         | Target     | integer  | Binary variable indicating loan default (1 = default, 0 = no default).      | 0                        |

**Data Dictionary for Uncertainty**


| Feature        | Mean        | Std Dev    | SE        | CI Lower    | CI Upper    | Min   | Max    | IQR       | N      | Qualitative Uncertainty                                                |
| -------------- | ----------- | ---------- | --------- | ----------- | ----------- | ----- | ------ | --------- | ------ | ---------------------------------------------------------------------- |
| Age            | 43.498306   | 14.990258  | 0.029665  | 43.440163   | 43.556450   | 18.0  | 69.0   | 25.00     | 255347 | Moderate variability; broadly stable distribution across adult range   |
| Income         | 82499.3046  | 38963.0137 | 77.105820 | 82348.1772  | 82650.4320  | 15000 | 149999 | 67393.50  | 255347 | High uncertainty due to wide dispersion and strong heterogeneity       |
| LoanAmount     | 127578.8655 | 70840.7061 | 140.19015 | 127304.0928 | 127853.6382 | 5000  | 249999 | 122829.00 | 255347 | Very high variability; indicates diverse borrowing behavior            |
| CreditScore    | 574.264346  | 158.903867 | 0.314463  | 573.647999  | 574.880693  | 300   | 849    | 275.00    | 255347 | Moderate uncertainty; spread suggests meaningful credit heterogeneity  |
| MonthsEmployed | 59.541976   | 34.643376  | 0.068557  | 59.407604   | 59.676349   | 0     | 119    | 60.00     | 255347 | Moderate variability; workforce stability varies substantially         |
| NumCreditLines | 2.501036    | 1.117018   | 0.002211  | 2.496703    | 2.505368    | 1     | 4      | 1.00      | 255347 | Low uncertainty; discrete and tightly bounded distribution             |
| InterestRate   | 13.492773   | 6.636443   | 0.013133  | 13.467032   | 13.518515   | 2     | 25     | 11.48     | 255347 | Moderate-high uncertainty; wide spread reflects pricing risk variation |
| LoanTerm       | 36.025894   | 16.969330  | 0.033581  | 35.960075   | 36.091714   | 12    | 60     | 24.00     | 255347 | Moderate variability; mixed short- and long-term borrowing structures  |
| DTIRatio       | 0.500212    | 0.230917   | 0.000457  | 0.499316    | 0.501108    | 0.1   | 0.9    | 0.40      | 255347 | Low-moderate uncertainty; relatively centered with bounded spread      |
