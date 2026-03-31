# Jira Data Pipeline Requirement Document

## 1. Objective

The objective is to design and implement an automated data pipeline to extract Jira issue data for BI reporting.

Currently, the BI team manually exports data from Jira into Excel. This pipeline will automate the process to improve efficiency, consistency, and data availability.

---

## 2. Source System

- Platform: Jira Service Desk
- API: `/rest/api/3/search/jql`
- Project: CDP (CT-IS Power Platform Service Desk)

---

## 3. Data Requirements

The pipeline should extract the following fields:

### Core Fields
- Issue Key  
- Issue ID  
- Summary  
- Issue Type (Regular Solution Deployment)  
- Status  
- Priority  

### User Details
- Assignee Name  
- Assignee ID  
- Reporter Name  
- Reporter ID  

### Date Fields
- Created  
- Updated  
- Due Date  
- Resolved  

### Additional Fields
- Request Type (Custom Field)  
- Resolution  

---

## 4. Filtering Logic

Only fetch relevant issues:

```sql
project = "CDP"
AND issuetype = "Regular Solution Deployment"