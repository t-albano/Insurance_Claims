# Insurance Complaints Data Documentation

Data was collected from [`All Insurance Complaints`](https://data.texas.gov/dataset/Insurance-complaints-All-data/ubdr-4uff). Data was cleaned and filtered to be related to BCBSTX and its competitors. All columns contain no NULLs. 

Description of the 14 variables in `cleaned_insurance_complaint_data.xlsx`:

- `Complaint_filed_against`: String. Refers to company complaint was filed against. From `All Insurance Complaints`, multiple versions of each company was listed. They were consolidated into parent company, unless they were not obviously a Texas branch. Possible values include `BCBS`, `Humana`, `United Health`, `Cigna`, and `Aetna`.

- `Complaint_filed_by`: String. Refers to person/entity filing complaint. There are 23 different possible strings. 

- `Reason_complaint_filed`: String. Full string of reason complaint was filed, as stated in `All Insurance Complaints`. There are 12,670 unique strings.

- `Main_Reason`: String. First substring of `Reason_complaint_filed`, up to the first `;`. There are 121 unique strings. 

- `Sub_Reason`: String. Second substring of `Reason_complaint_filed`, up to the second `;`. There are 111 unique strings. If there was no subreason, it is listed as `None`.

- `Num_Stages`: Float. Number of substrings in `Reason_complaint_filed`, as each reason corresponded to the next stage in the complaint process. 

- `Confirmed_complaint`: String. Either a `Yes` or `No`. `No` indicates that complaint was unjustified.

- `Received_date`: Date. Date complaint was made. Goes from 10/5/2011 to 4/18/2023.

- `Month`: Integer. Month of `Received_date`.

- `Closed_date`: Date. Date complaint case was concluded. Goes from 7/11/2012 to 4/27/2023

- `Claim_Length`: Integer. Number of days between `Received_date` and `Closed_date`. Spans from 0 days to 855 days.

- `Complaint_type`: String. More specific classification of claim under Life, Accident and Health. 15 unique strings. 

- `Coverage_level`: String. Coverage level of person who filed complaint. 7

- `Respondent_type`: String. Only will show `Organization`. This refers to the companies dealt with the complaint. This includes: `Group A&H`, `Individual A & H`, `XX-State Specific`, `High Deductable Ben Plan`, `Discount Health Care Program`, `Federal High Risk Pool`, and `Credit Disability`.

- `Num_Others`: Float. Number of substrings/people in `Others Involved` from `All Insurance Complaints`.
