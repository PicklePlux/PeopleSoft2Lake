# 🛠️ PeopleSoft2Lake

**PeopleSoft2Lake** is a secure ETL pipeline designed to modernize HR data infrastructure by migrating records from legacy **PeopleSoft Oracle** systems to a scalable **AWS data lake** environment. Leveraging **AWS Glue**, **Amazon Redshift**, and **Athena**, the pipeline ensures accurate, auditable, and high-performance data delivery for downstream analytics and reporting.

Built for enterprise-grade compliance and performance, PeopleSoft2Lake includes comprehensive schema modeling, data cleansing routines, and automated post-migration validation to ensure data integrity and audit readiness.

## 📌 Features

- 🔄 **ETL Automation**:
  - AWS Glue jobs for schema mapping, transformation, and enrichment
  - Automated data ingestion from Oracle to S3 with schema enforcement
  - Redshift Spectrum for federated queries on historical + real-time data

- 🧹 **Data Cleansing & Validation**:
  - Cleans legacy HR records using Python scripts within Glue
  - Validates row-level accuracy with checksum and cross-source comparison
  - Flags anomalies for manual inspection and correction

- 🔍 **Post-Migration Auditing**:
  - Athena queries to confirm row counts and value integrity
  - Metadata logging and lineage tracking for every batch
  - Audit dashboards for compliance and operational oversight

- 🔒 **Security & Access Control**:
  - S3 bucket policies and IAM roles for fine-grained access
  - Encryption at rest and in transit (KMS + TLS)
  - CloudTrail logs and alerting for suspicious activity

## 🧰 Tech Stack

- **ETL Orchestration**: AWS Glue, Python
- **Data Lake**: Amazon S3, Redshift, Athena
- **Source System**: PeopleSoft Oracle DB
- **Validation & Logging**: AWS CloudWatch, CloudTrail, Lambda
- **Security**: AWS IAM, KMS, TLS/SSL

## 🚀 Getting Started

### Prerequisites

- AWS Account with access to Glue, S3, Redshift, and Athena
- Oracle DB credentials and schema export access
- Python 3.9+ for local script testing

### Deployment Steps

```bash
# Clone the ETL configuration repository
git clone https://github.com/your-username/peoplesoft2lake.git
cd peoplesoft2lake

# Deploy resources using CloudFormation
aws cloudformation deploy --template-file infra.yml --stack-name PeopleSoft2LakeStack

# Trigger initial Glue job manually or via Lambda scheduler
