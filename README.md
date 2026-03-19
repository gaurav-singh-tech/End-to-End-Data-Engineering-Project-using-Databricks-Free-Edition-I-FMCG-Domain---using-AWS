<div align="center">

# 🚀 End-to-End Data Engineering Project  
## Using Databricks Free Edition | FMCG Domain | AWS Cloud

[![Build Status](https://img.shields.io/badge/Build-Passing-brightgreen?style=for-the-badge&logo=github)](https://github.com/gaurav-singh-tech)
[![Jupyter Notebook](https://img.shields.io/badge/Language-Jupyter%20Notebook-orange?style=for-the-badge&logo=jupyter)](https://jupyter.org/)
[![Databricks](https://img.shields.io/badge/Framework-Databricks-red?style=for-the-badge&logo=databricks)](https://databricks.com/)
[![AWS](https://img.shields.io/badge/Cloud-AWS-FF9900?style=for-the-badge&logo=amazonaws)](https://aws.amazon.com/)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python)](https://www.python.org/)
[![License MIT](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

**A comprehensive enterprise-grade data engineering solution for FMCG analytics**

[📚 Documentation](#-documentation) • [🏗️ Architecture](#-architecture) • [⚙️ Setup](#-setup) • [🎯 Features](#-key-features)

</div>

---
#FMCG_DASHBOARD


![Uploading FMCG_Dashboard.jpg…]()


## 📋 Table of Contents

- [📖 Overview](#-overview)
- [🎯 Key Features](#-key-features)
- [🏗️ Architecture](#-architecture)
- [📊 Project Structure](#-project-structure)
- [⚙️ Technical Stack](#-technical-stack)
- [🚀 Getting Started](#-getting-started)
- [📈 Data Pipeline](#-data-pipeline)
- [🔧 Configuration](#-configuration)
- [📚 Documentation](#-documentation)
- [🤝 Contributing](#-contributing)
- [📝 License](#-license)
- [👨‍💼 Author](#-author)

---

## 📖 Overview

**Adaptive RAG - End-to-End Data Engineering Solution** is a production-ready data engineering platform that leverages **Databricks Free Edition** and **AWS Cloud** infrastructure to build a comprehensive data lake and analytics solution for the FMCG (Fast-Moving Consumer Goods) industry.

This project demonstrates enterprise-level data engineering practices including:
- ✅ **Medallion Architecture** (Bronze → Silver → Gold layers)
- ✅ **Multi-source Data Integration** (Parent & Child Company Data, Orders)
- ✅ **Data Quality Validation** & Transformation
- ✅ **Scalable Cloud Infrastructure** on AWS
- ✅ **Real-time & Batch Processing** using Apache Spark
- ✅ **Dimension & Fact Table Processing**

---

## 🎯 Key Features

<table>
<tr>
<td width="50%">

### 🌟 Core Capabilities

- **Multi-Layer Data Architecture**
  - Bronze Layer (Raw Data)
  - Silver Layer (Cleaned Data)
  - Gold Layer (Analytics Ready)

- **Advanced Data Processing**
  - Parent Company Hierarchy Management
  - Child Company Aggregation
  - Order Fact Table Processing

- **Data Quality Assurance**
  - Schema Validation
  - Duplicate Detection
  - Null Value Handling

</td>
<td width="50%">

### ⚡ Performance & Scalability

- **High-Performance Processing**
  - Apache Spark Distributed Computing
  - Optimized Partitioning Strategy
  - Efficient Data Compression

- **Cloud-Native Architecture**
  - AWS S3 for Data Storage
  - Databricks Workspace Integration
  - Scalable Compute Resources

- **Enterprise Grade**
  - Audit Logging
  - Data Lineage Tracking
  - Error Handling & Recovery

</td>
</tr>
</table>

---

## 🏗️ Architecture

### High-Level System Architecture

```
┌──────────────────────────────────────────────────────────────────────┐
│                         AWS Cloud Environment                        │
├──────────────────────────────────────────────────────────────────────┤
│                                                                      │
│  ┌──────────────────────────────────────────────────────────────┐  │
│  │                     Data Sources                             │  │
│  │  ┌────────────┐  ┌────────────┐  ┌────────────┐             │  │
│  │  │   Parent   │  │   Child    │  │   Orders   │             │  │
│  │  │  Company   │  │  Company   │  │     Data   │             │  │
│  │  └���───────────┘  └────────────┘  └────────────┘             │  │
│  └────────────────────┬─────────────────────────────────────────┘  │
│                       │                                             │
│                       ▼                                             │
│  ┌──────────────────────────────────────────────────────────────┐  │
│  │            AWS S3 (Raw Data - Bronze Layer)                 │  │
│  │         gs://bucket_name/bronze/                            │  │
│  └────────────────────┬─────────────────────────────────────────┘  │
│                       │                                             │
│       ┌───────────────┼───────────────┐                             │
│       │               │               │                             │
│       ▼               ▼               ▼                             │
│  ┌─────────┐  ┌──────────┐  ┌──────────────┐                       │
│  │ Parent  │  │  Child   │  │   Orders     │                       │
│  │ Company │  │ Company  │  │   Dimension  │                       │
│  │ Proc    │  │ Proc     │  │   Processing │                       │
│  └────┬────┘  └────┬─────┘  └───────┬──────┘                       │
│       │             │               │                              │
│       └─────────────┼───────────────┘                              │
│                     │                                              │
│                     ▼                                              │
│  ┌──────────────────────────────────────────────────────────────┐  │
│  │      AWS S3 (Processed Data - Silver Layer)                 │  │
│  │    gs://bucket_name/silver/                                 │  │
│  └────────────────────┬─────────────────────────────────────────┘  │
│                       │                                             │
│                       ▼                                             │
│  ┌──────────────────────────────────────────────────────────────┐  │
│  │      AWS S3 (Analytics Ready - Gold Layer)                  │  │
│  │    gs://bucket_name/gold/                                   │  │
│  └────────────────────┬─────────────────────────────────────────┘  │
│                       │                                             │
│                       ▼                                             │
│  ┌──────────────────────────────────────────────────────────────┐  │
│  │           Databricks Workspace                               │  │
│  │   • Data Exploration & Analysis                             │  │
│  │   • ML Model Development                                    │  │
│  │   • Report Generation                                       │  │
│  └──────────────────────────────────────────────────────────────┘  │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Data Processing Pipeline

<table>
<thead>
<tr style="background-color: #f0f0f0;">
<th align="left" width="20%">Stage</th>
<th align="left" width="20%">Layer</th>
<th align="left" width="30%">Processing</th>
<th align="left" width="30%">Output</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>1. Ingestion</strong></td>
<td>Bronze</td>
<td>Raw data from multiple sources</td>
<td>Parquet files in S3</td>
</tr>
<tr style="background-color: #f9f9f9;">
<td><strong>2. Transformation</strong></td>
<td>Silver</td>
<td>Cleansing, validation, enrichment</td>
<td>Standardized tables</td>
</tr>
<tr>
<td><strong>3. Aggregation</strong></td>
<td>Gold</td>
<td>Business logic, dimension/fact tables</td>
<td>Analytics-ready datasets</td>
</tr>
<tr style="background-color: #f9f9f9;">
<td><strong>4. Analytics</strong></td>
<td>Analytics</td>
<td>BI tools, dashboards, reports</td>
<td>Business insights</td>
</tr>
</tbody>
</table>

---

## 📊 Project Structure

```
End-to-End-Data-Engineering-Project/
│
├── 📁 1_setup/
│   ├── Workspace Setup Notebooks
│   ├── Cluster Configuration
│   ├── Library Installation
│   └── Environment Variables
│
├── 📁 1_parent_company/
│   ├── Parent Company Data Loading
│   ├── Hierarchy Validation
│   ├── Bronze → Silver Transformation
│   └── Dimension Table Creation
│
├── 📁 2_dimension_data_processing/
│   ├── Dimension Data Extraction
│   ├── Slowly Changing Dimensions (SCD)
│   ├── Reference Data Management
│   └── Dimension Table Aggregation
│
├── 📁 3_fact_data_processing/
│   ├── Order Fact Table Processing
│   ├── Transaction Data Aggregation
│   ├── Metric Calculation
│   └── Fact Table Optimization
│
├── 📁 child_company_data/
│   ├── Child Company Integration
│   ├── Company Hierarchy Linking
│   ├── Multi-level Aggregation
│   └── Subsidiary Data Processing
│
├── 📁 orders/
│   ├── Order Data Ingestion
│   ├── Transaction Processing
│   ├── Order Status Tracking
│   └── Revenue Metrics Calculation
│
└── 📄 README.md
    └── Project Documentation
```

---

## ⚙️ Technical Stack

### 🔧 Core Technologies

| Component | Technology | Version | Purpose |
|-----------|-----------|---------|---------|
| **Big Data Framework** | Apache Spark | 3.x | Distributed data processing |
| **Data Platform** | Databricks | Free Edition | Unified analytics workspace |
| **Cloud Provider** | AWS | Current | Cloud infrastructure |
| **Storage** | AWS S3 | Latest | Data lake storage |
| **Languages** | Python, SQL, Scala | Latest | ETL scripting |
| **Notebooks** | Jupyter | Latest | Interactive development |

### 📚 Key Libraries & Tools

```
Data Processing:
├── PySpark (Distributed computing)
├── Pandas (Data manipulation)
└── NumPy (Numerical operations)

Data Quality:
├── Great Expectations
├── Deequ
└── Custom Validation Scripts

Cloud & DevOps:
├── AWS CLI
├── Databricks CLI
├── Terraform (Infrastructure as Code)
└── Git (Version Control)
```

---

## 🚀 Getting Started

### ✅ Prerequisites

Before you begin, ensure you have:

- ✓ AWS Account with appropriate permissions
- ✓ Databricks Free Edition Workspace
- ✓ Python 3.8+ installed locally
- ✓ AWS CLI configured with credentials
- ✓ Git for version control
- ✓ Jupyter Notebook or Databricks Notebook editor
- ✓ Basic knowledge of PySpark and SQL

### 📥 Installation & Setup

#### Step 1: Clone the Repository
```bash
git clone https://github.com/gaurav-singh-tech/End-to-End-Data-Engineering-Project-using-Databricks-Free-Edition-I-FMCG-Domain---using-AWS.git

cd End-to-End-Data-Engineering-Project-using-Databricks-Free-Edition-I-FMCG-Domain---using-AWS
```

#### Step 2: Set Up Databricks Workspace
```bash
# Install Databricks CLI
pip install databricks-cli

# Configure Databricks connection
databricks configure --token

# Test connection
databricks workspace list
```

#### Step 3: Configure AWS Credentials
```bash
# Configure AWS CLI
aws configure

# Verify S3 access
aws s3 ls
```

#### Step 4: Create Required S3 Buckets
```bash
# Create data lake buckets
aws s3 mb s3://your-org-data-bronze/
aws s3 mb s3://your-org-data-silver/
aws s3 mb s3://your-org-data-gold/

# Enable versioning and encryption
aws s3api put-bucket-versioning \
  --bucket your-org-data-bronze \
  --versioning-configuration Status=Enabled
```

#### Step 5: Set Up Environment Variables
Create `.env` file in the project root:
```env
# AWS Configuration
AWS_REGION=us-east-1
AWS_ACCESS_KEY_ID=your_access_key
AWS_SECRET_ACCESS_KEY=your_secret_key

# S3 Buckets
S3_BRONZE_BUCKET=your-org-data-bronze
S3_SILVER_BUCKET=your-org-data-silver
S3_GOLD_BUCKET=your-org-data-gold

# Databricks Configuration
DATABRICKS_HOST=https://your-workspace.cloud.databricks.com
DATABRICKS_TOKEN=your_token
```

#### Step 6: Import Notebooks to Databricks
```bash
# Upload notebooks to workspace
databricks workspace import_directory \
  ./notebooks \
  /Users/your-email@company.com/fmcg-project
```

---

## 📈 Data Pipeline

### Detailed Processing Workflow

```
INPUT DATA
    │
    ├──► [1_SETUP]
    │    └─ Initialize workspace & clusters
    │
    ├──► [1_PARENT_COMPANY]
    │    ├─ Load company hierarchy
    │    ├─ Validate structure
    │    └─ Create dimension table
    │
    ├──► [2_DIMENSION_DATA_PROCESSING]
    │    ├─ Extract product dimensions
    │    ├─ Handle slowly changing dimensions
    │    └─ Create reference tables
    │
    ├──► [3_FACT_DATA_PROCESSING]
    │    ├─ Process order transactions
    │    ├─ Calculate metrics
    │    └─ Optimize fact tables
    │
    ├──► [CHILD_COMPANY_DATA]
    │    ├─ Integrate subsidiary data
    │    ├─ Link to parent hierarchy
    │    └─ Aggregate across companies
    │
    └──► [ORDERS]
         ├─ Process order details
         ├─ Track transaction status
         └─ Generate revenue reports

ANALYTICS OUTPUT
    └─ Business Intelligence Ready Data
```

---

## 🔧 Configuration

### Spark Configuration
```python
# Optimal Spark settings for Databricks Free Edition
spark.conf.set("spark.sql.shuffle.partitions", "8")
spark.conf.set("spark.sql.adaptive.enabled", "true")
spark.conf.set("spark.sql.adaptive.skewJoin.enabled", "true")
spark.conf.set("spark.databricks.delta.optimizeWrite.enabled", "true")
```

### Data Processing Parameters

| Parameter | Value | Description |
|-----------|-------|-------------|
| Partition Size | 256 MB | Optimal partition granularity |
| Shuffle Partitions | 8 | Number of partitions for shuffles |
| Batch Size | 10,000 | Records per batch |
| Memory per Executor | 4 GB | Free tier allocation |
| Number of Executors | 1 | Free tier limitation |

---

## 📚 Documentation

### Notebook Index

| Notebook | Purpose | Estimated Time |
|----------|---------|-----------------|
| `1_setup/01_workspace_setup` | Initial workspace configuration | 5 mins |
| `1_parent_company/01_load_data` | Load parent company hierarchy | 10 mins |
| `1_parent_company/02_transform_data` | Transform to Silver layer | 15 mins |
| `2_dimension_data_processing/01_dimension_extract` | Extract dimensions | 20 mins |
| `3_fact_data_processing/01_fact_processing` | Process fact tables | 25 mins |
| `child_company_data/01_integration` | Integrate subsidiary data | 15 mins |
| `orders/01_order_processing` | Process order data | 20 mins |

### Key Concepts

#### 🔹 Medallion Architecture
- **Bronze Layer**: Raw, unprocessed data as received from sources
- **Silver Layer**: Cleaned, deduplicated, validated data
- **Gold Layer**: Business logic applied, aggregated, analytics-ready data

#### 🔹 Delta Lake Format
All tables stored in Delta format for:
- ACID transactions
- Schema enforcement
- Time travel capabilities
- Unified batch & streaming

#### 🔹 Data Lineage
Track data flow from source to analytics through automated lineage tracking

---

## 🤝 Contributing

We welcome contributions! Here's how to get involved:

### Steps to Contribute

1. **Fork the Repository**
   ```bash
   gh repo fork gaurav-singh-tech/End-to-End-Data-Engineering-Project-using-Databricks-Free-Edition-I-FMCG-Domain---using-AWS
   ```

2. **Create Feature Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make Your Changes**
   - Follow PEP 8 guidelines
   - Add docstrings to functions
   - Include inline comments for complex logic

4. **Commit with Clear Messages**
   ```bash
   git commit -m "feat: Add new data transformation logic for product dimensions"
   ```

5. **Push to Your Fork**
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Create Pull Request**
   - Describe changes clearly
   - Reference any related issues
   - Request code review

### Contribution Guidelines

- ✅ Follow existing code style
- ✅ Add unit tests for new features
- ✅ Update documentation
- ✅ Test locally before submitting
- ✅ Be respectful and constructive

---

## 🔐 Best Practices

### Security

- 🔒 Never commit credentials to Git
- 🔒 Use AWS IAM roles instead of access keys
- 🔒 Enable S3 bucket encryption
- 🔒 Use Databricks token rotation
- 🔒 Implement data masking for sensitive columns

### Performance

- ⚡ Partition data by logical keys
- ⚡ Use Delta merge for incremental updates
- ⚡ Implement proper indexing strategies
- ⚡ Monitor cluster resource utilization
- ⚡ Optimize Spark shuffle partitions

### Reliability

- 🛡️ Implement comprehensive error handling
- 🛡️ Add data quality checks
- 🛡️ Use idempotent operations
- 🛡️ Maintain audit logs
- 🛡️ Test edge cases thoroughly

---

## 🎯 Use Cases

This project is perfect for:

| Use Case | Application |
|----------|-------------|
| **Supply Chain Analytics** | Track orders, suppliers, and distribution |
| **Sales Performance** | Analyze sales by company, region, product |
| **Customer Insights** | Identify patterns and customer segments |
| **Inventory Management** | Monitor stock levels and movement |
| **Financial Analysis** | Revenue tracking and forecasting |
| **Data Lake Development** | Learn medallion architecture pattern |
| **ETL Pipeline Design** | Understand production-grade pipelines |

---

## 📊 Performance Metrics

### Typical Processing Times (Free Edition)

| Operation | Time | Notes |
|-----------|------|-------|
| Load Parent Company | 2-3 mins | 100K records |
| Transform to Silver | 3-5 mins | Deduplication & validation |
| Create Dimensions | 2-3 mins | ~50K unique values |
| Process Orders | 5-8 mins | 1M+ transactions |
| Generate Gold Tables | 3-4 mins | Aggregations |
| **Total Pipeline** | **15-25 mins** | Full run end-to-end |

---

## 🚨 Troubleshooting

### Common Issues

**Issue: S3 Access Denied**
```bash
# Solution: Verify IAM permissions
aws iam get-user
aws s3 ls s3://your-bucket/ --recursive
```

**Issue: Out of Memory**
```python
# Solution: Increase partition count
spark.conf.set("spark.sql.shuffle.partitions", "16")
```

**Issue: Notebook Import Failed**
```bash
# Solution: Check Databricks token and workspace URL
databricks workspace list
```

---

## 📞 Support & Resources

### Documentation Links
- 📖 [Databricks Documentation](https://docs.databricks.com/)
- 📖 [Apache Spark Docs](https://spark.apache.org/docs/)
- ��� [AWS S3 Guide](https://docs.aws.amazon.com/s3/)
- 📖 [Delta Lake Docs](https://delta.io/)

### Community
- 💬 [Databricks Community](https://community.databricks.com/)
- 💬 [Stack Overflow - Databricks](https://stackoverflow.com/questions/tagged/databricks)
- 💬 [Reddit - r/dataengineering](https://reddit.com/r/dataengineering/)

---

## 📈 Roadmap

### Future Enhancements

- [ ] Add real-time streaming with Kafka
- [ ] Implement ML pipelines for forecasting
- [ ] Create Power BI/Tableau dashboards
- [ ] Add data quality monitoring
- [ ] Implement cost optimization strategies
- [ ] Expand to multi-cloud architecture
- [ ] Add automated testing framework
- [ ] Create production CI/CD pipeline

---

## 📝 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2026 Gaurav Singh

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 👨‍💼 Author

<div align="center">

**Gaurav Singh**

[![GitHub](https://img.shields.io/badge/GitHub-gaurav--singh--tech-black?style=for-the-badge&logo=github)](https://github.com/gaurav-singh-tech)
[![Email](https://img.shields.io/badge/Email-Contact%20Me-red?style=for-the-badge&logo=gmail)](mailto:your-email@example.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin)](https://linkedin.com/in/your-profile)

*Data Engineer | Cloud Architect | Big Data Enthusiast*

</div>

---

## 🙏 Acknowledgments

This project was built with inspiration from:
- Databricks Engineering Best Practices
- AWS Data Lake Architecture Patterns
- Modern Data Stack Principles
- Open Source Community Contributions

### Special Thanks
- 🙌 Databricks Community for support
- 🙌 AWS Documentation team
- 🙌 Apache Spark contributors
- 🙌 Fellow data engineers for feedback

---

<div align="center">

### ⭐ If you found this project helpful, please consider giving it a star!

**[⬆ back to top](#-end-to-end-data-engineering-project)**

---

**Last Updated**: March 16, 2026  
**Status**: 🟢 Active Development  
**Version**: 1.0.0  
**Maintained By**: Gaurav Singh

</div>
