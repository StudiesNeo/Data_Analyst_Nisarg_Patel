# Data_Analyst_Nisarg_Patel
# 🎓 UCW Academic Department AWS Cloud Management

  This project builds a serverless, end‑to‑end AWS pipeline for UCWA’s academic department to analyze workload distribution. I ingest CSV into S3, profile and clean the data via Glue DataBrew, transform and enrich it using Glue ETL and crawlers, then catalogue and query it in Athena. The result is a scalable, maintainable analytics workflow that provides timely insights for academic planning and resourcing.
---

## 1. Project Overview

- **Title:** Perform descriptive analysis to identify whether the student demographics are linked to a lower retention rate.    
- **Scope:** Examine how student demographics—such as student ID, enrollment status, ethnicity, and age relate to lower retention rates to identify at-risk groups.

---

## 2. Activities Performed 

**Business Question Development**  
   - Which student demographics are associated with lower retention rates?
   - Developed goals and objectives
   - Identified the cause factors
   - Created an organized Excel file for structured analysis.

Image 1: Structured data file 
<img width="1786" alt="Screenshot 2025-06-23 at 4 22 05 PM" src="https://github.com/user-attachments/assets/5c50bd46-3f57-4305-bdcb-ca36353471e4" />

**Fishbone Diagram** 
   - Using a Fishbone diagram, visualize the cause factors related to the student demographics.

Image 2: Fishbone diagram for cause factor analysis.
<img width="1785" alt="Fishbone Design" src="https://github.com/user-attachments/assets/8324a0f3-0ec3-4293-b729-8893e7261279" />

**Designed and organized **
S3 data lake bucket: `academic-raw-nis` with folders for:**
   - Course Enrollments
   - Faculty Assignments
   - Student Demographics
   - Academic Performance
   - Graduation and Retention

Image 3: S3 bucket creation and storage location.
<img width="1785" alt="Database Design" src="https://github.com/user-attachments/assets/3cd686cc-a3e7-40e4-9f7a-8eb468481587" />

**AWS Environment Configuration**
  1. Configured AWS essentials for cloud architecture.
     - **Custom VPC**: `Academic-VPC-nis`
     - **Security Group**: `Academic-SG-nis`
     - **Network Interface**: `Academic-NIC-nisarg`
     - **EC2 Instance** for secure analytics

**Designed the Data Lack Visuals**
   - Designed the data lake visualization to understand cloud architecture more clearly. 

Image 4: Data lack Design
<img width="1785" alt="Data Lake Design" src="https://github.com/user-attachments/assets/e1c744ae-50a7-4e5e-a073-5d5a4a913b68" />

**Tools**
     - Excel
     - Draw.io
     - AWS S3
     - AWS EC2
     - AWS CLI

**Deliverables**
     - Business analysis in Excel format
     - Cause-and-effect (Fishbone) diagram
     - Data lake folder hierarchy in AWS S3
     - AWS Academy progress report (PDF)

Week 3 – Data Profiling, Cleaning & Cost Evaluation

**Project Title**: Data Quality Enhancement and AWS Cost Analysis for Student Retention Analysis.

**Objective**:
Profile and clean Week 2 datasets, then estimate the monthly and annual AWS costs for storing them in S3 and processing them with Glue DataBrew using the AWS Pricing Calculator.

**Activities Performed:**

    Cost Evolution 
    
    - Used AWS Pricing Calculator to evaluate S3 storage and request costs
    - Parameters:
    - 1 GB storage
    - Region: US East (N. Virginia)
    - Monthly cost: ~$0.02  
    - Annual estimate: ~$0.24 

Image 5: Cost Estimation 
<img width="873" alt="Screenshot 2025-06-23 at 5 05 16 PM" src="https://github.com/user-attachments/assets/e0f9d62e-f9a8-4e22-bcab-97ef9c3e12a8" />

2.	Data Cleaning & Profiling:
   
    - Employed AWS Glue DataBrew to profile and cleanse academic datasets using its visual, no-code transformations.
    - Removed null entries, deduplicated data, and standardized formats (e.g., dates, names) across datasets
    - Exported cleaned data in Parquet and CSV formats to structured S3 storage
    - Documented transformation steps in Excel to ensure transparency, reproducibility, and auditability

Image 6: Data Profile Overview. 

![image](https://github.com/user-attachments/assets/c63a0d91-93f1-4669-bacb-fcc08cd35e58)

Image 7: Projects 

![image](https://github.com/user-attachments/assets/93398d69-e883-4224-a009-02a173948c1d)

**Tools Used:**

* AWS S3,
* AWS Glue DataBrew,
* AWS Pricing Calculator,
* Excel

**Deliverables:**

* Cleaned datasets (CSV/Parquet)
* Cost analysis report (PDF)
* Data profiling metrics
* Data-cleaning design documented in Excel

**Key Insights**
* Minimal S3 storage cost validates scalability and budget-friendliness, making it ideal for expanding data lakes
* Cleaned, analytics-ready datasets (CSV/Parquet) facilitate seamless downstream processing
* Profiling revealed enhanced data consistency, ensuring reliable academic workload metrics

**Week 4 – ETL Pipeline: Enrichment and Summarization**

**Project Title: Building an End-to-End ETL Pipeline to Enrich Student Demographics for Retention Analysis**

**Objective:**
  - Design and implement an automated ETL pipeline leveraging AWS to integrate, transform, enrich, and summarize student demographic and academic datasets, enabling data-driven insights into factors affecting retention.

**Activities Performed:**

**ETL Pipeline Design*

**Extraction:** Retrieved cleaned demographic and retention data from the “cleaning zone” in S3.

**Data Joins for Enrichment:*

Applied INNER JOINs to combine student demographics with retention records, ensuring linked data for analysis.

Used LEFT JOINs to capture demographic records.

*Standardization:* Normalized categorical demographic attributes (e.g., gender, ethnicity) and student ID fields consistently across datasets.

Image 8: DAP Design 

![W4_Drawio](https://github.com/user-attachments/assets/fc2d143f-bb8c-4c57-92fd-6cb8781aa3b9)

Image 9: ETL

![W4_Visual_ETL](https://github.com/user-attachments/assets/671164d1-36b8-40ea-8365-d55dfa921862)

**2. Summarization**

    - Utilized Amazon Athena to run reusable SQL queries that:
    - Calculated average faculty workload
    - Identified the count of overburdened faculty
    - Analyzed weekly trends in faculty load versus course demand
    - All query scripts were documented for future reference and reuse.

Image 10: Analytical Quary 

![W4_Gender_Query](https://github.com/user-attachments/assets/4ed3b31b-4184-411c-8322-428163d44a60)

Image 11: Cost Estimation 

![W5_Billing](https://github.com/user-attachments/assets/49341fc7-9054-48ba-b268-c6c86ce704da)

4.	Output & Storage:

    •	Final data exported to **S3 curated zone**:
    •	Output formats: CSV, JSON, Parquet

Image 12: Output and Storage 
![W4_Datacatalog](https://github.com/user-attachments/assets/6ff901dd-7fe5-465a-9930-54f0f4c77002)

**Tools Utilized:**

AWS Glue Studio · AWS Athena · CloudWatch · draw.io · Excel 

**Deliverables Produced:**

    - Curated, processed datasets
    - ETL job designs and executable scripts
    - ETL cost analysis report (PDF)
    - Athena query result summaries
    - CloudWatch alert and monitoring configurations 


**Key Findings:**

    - 28% of faculty teach more than four courses during peak semesters
    - Week 2 of each term consistently emerges as the highest workload period
    - Data enrichment enabled precise insights at the department level

---

**AWS Deployment and Service Models**

We evaluated UCW’s on‑premise Data Center against a modern AWS-based cloud model and found that migrating to AWS significantly enhances scalability, security, availability, and overall system agility, while reducing infrastructure constraints.

Image 13: Traditional Computing Model vs Cloud Computing Model

| **Aspect**             | **Traditional Computing Model**                    | **Cloud Computing Model (AWS)**                                                                  |
| ---------------------- | -------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **Dataset Location**   | Stored locally on UCW servers and hard drives      | Stored in AWS S3 using a structured multi-zone format (Raw → Cleaned → Curated)                  |
| **Access**             | Restricted to VPN/university network               | Accessible globally via secure IAM roles and policies                                            |
| **Privacy Management** | Manual policy management with limited auditability | Fine-grained IAM controls, encryption at rest, comprehensive logging, and tagging for compliance |


![Screenshot 2025-06-23 at 5 53 00 PM](https://github.com/user-attachments/assets/055fd59b-e673-4bd2-b37f-0e98440caf81)

Image 14: Data Location and Modelling

| **Cloud Model**   | **Dataset Location**                                                | **Access**                                                     | **Privacy & Security**                                                            |
| ----------------- | ------------------------------------------------------------------- | -------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| **Private Cloud** | Stored internally on university servers                             | Restricted to the university’s internal network                | Fully managed in-house, limited auditing capabilities                             |
| **Public Cloud**  | Stored in AWS S3 with a structured data-lake layout                 | Accessible over the internet via AWS IAM authentication        | Managed through IAM policies, MFA, encryption, and logging                        |
| **Hybrid Cloud**  | Older student records on-premises; new data stored in AWS           | Access via a combination of internal network and cloud console | Requires integrated security policies spanning on-premises and cloud environments |
| **Multi-Cloud**   | Distributed across multiple providers (AWS S3, Google Cloud, Azure) | Separate access mechanisms per provider                        | Privacy/compliance varies across providers and must be managed per platform       |


![Screenshot 2025-06-23 at 6 20 39 PM](https://github.com/user-attachments/assets/e0540d6f-5246-426a-9adf-39d3f41c4cb7)

Image 15: Data Location and Modelling

![Screenshot 2025-06-23 at 6 36 28 PM](https://github.com/user-attachments/assets/2062b409-c6b7-48f2-9a0c-05920ad66530)


| **Model** | **Dataset Location**                       | **Access**                                        | **Privacy Management**                                         |
| --------- | ------------------------------------------ | ------------------------------------------------- | -------------------------------------------------------------- |
| **IaaS**  | Data uploaded manually to EC2 instances    | Requires EC2 SSH login                            | User controls firewalls and permissions                        |
| **PaaS**  | Stored in S3 and processed via AWS Glue    | Launched through scheduled or on-demand Glue jobs | IAM roles manage data access and job execution                 |
| **SaaS**  | Accessed through a web application/browser | Simple user login                                 | Privacy and security primarily managed by the service provider |

**AWS Cloud Foundation Module 1 Knowledge Check Result**

  -  This module strengthened my core understanding of cloud computing, highlighting how cloud models offer significantly greater agility, cost savings, and governance compared to traditional university IT infrastructure.

AWS Academy Module 1 Knowledge Check

Image 16: Module 1 Knowledge Check
<img width="951" alt="Screenshot 2025-06-23 at 10 38 21 PM" src="https://github.com/user-attachments/assets/f0b0be21-ca68-4691-bf35-c7a63fa6d44e" />

---

**AWS Cost Analysis**

**Total Cost of Ownership – Delaware North (Paraphrased):**

Delaware North’s transition to AWS resulted in significant cost savings and enhanced efficiency. The company retired 205 servers, cutting \$3.5 million in expenses over five years. Additionally, it shortened deployment timelines from several weeks to just one day. By moving to AWS, Delaware North boosted agility while substantially lowering infrastructure costs and speeding up operations, making it a smart choice for organizations aiming for high returns on investment.

Image 17: Total cost of ownership - Delaware North

![Screenshot 2025-06-23 at 10 47 42 PM](https://github.com/user-attachments/assets/f1562af9-43f6-442d-bfbb-84af68a452b9)

---
**AWS Pricing Calculator**

Three components were calculated for an academic data project:
1.	Data Ingestion – $15.48/year
2.	Data Profiling and cleaning – $46.44/year
3.	Data Analysis using Athena – $86.76/year

Image 18: Data storage 

<img width="1784" alt="Screenshot 2025-06-23 at 11 02 05 PM" src="https://github.com/user-attachments/assets/19c99bdc-d91b-4af6-8c0e-f6558c777a03" />

Image 19: Data Profiling and Cleaning

<img width="1784" alt="Screenshot 2025-06-23 at 11 07 54 PM" src="https://github.com/user-attachments/assets/8c267cce-f875-4cc0-b5d7-628de020276c" />

Image 20: Data Analysis

<img width="1784" alt="Screenshot 2025-06-23 at 11 14 22 PM" src="https://github.com/user-attachments/assets/ac792b3f-2be3-4219-a4ff-74ff3c8c8418" />















