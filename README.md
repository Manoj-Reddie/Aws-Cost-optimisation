# 💰 AWS Cloud Cost Optimization – Identifying Stale Resources

## 🚀 Overview

This project provides an automated solution to reduce AWS storage costs by identifying and deleting stale EBS snapshots that are no longer associated with any active EC2 instances. The solution uses an AWS Lambda function, triggered by CloudWatch Events, and built with Python and Boto3.

## 🔍 Identifying Stale EBS Snapshots

### 📋 Description

The AWS Lambda function:

- Fetches all EBS snapshots owned by the account (`self`).
- Retrieves all **active EC2 instances** (both running and stopped).
- Cross-references EBS snapshot volumes against those associated with active instances.
- Deletes **unused (stale)** snapshots to reduce storage costs.
- Sends notifications via **Amazon SNS** before deleting any snapshot.

### 💡 Key Features

- ✅ Automated cleanup of unused EBS snapshots  
- 🧠 Intelligent filtering to ensure only stale resources are targeted  
- 📉 Reduces AWS monthly storage costs (up to 25%)  
- 🔔 Notification alerts using **SNS** for visibility and control  
- 🧰 Built using **AWS Lambda**, **CloudWatch Events**, **Python**, and **Boto3**

## 📦 Requirements

- AWS account with access to EC2, Lambda, and SNS
- IAM Role with appropriate permissions (`ec2:DescribeSnapshots`, `ec2:DeleteSnapshot`, etc.)
- Python 3.x with Boto3 (if developing locally)

## 🛠 Setup & Deployment

1. Clone the repository and set up your Lambda function using the provided Python script.
2. Configure CloudWatch Events to trigger the Lambda function on a schedule (e.g., daily).
3. Set up an SNS topic and subscription to receive pre-deletion notifications.
4. Deploy using the AWS Console, AWS CLI, or a framework like AWS SAM.

