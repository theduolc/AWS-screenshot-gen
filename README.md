# AWS Screenshot Generator <br>

Description: Takes a screenshot of a website after entering a URL and returns the link to the screenshot in an S3 bucket. <br>

+ Files for creating the infrastructure (EC2, S3 bucket) using Terraform
+ Security groups for accessing the API using Terraform
+ Python code for creating, uploading to the S3 bucket, and returning the URL to the saved screenshot

# AWS Screenshot Generator

## 🚀 Overview

**AWS Screenshot Generator** is a simple AWS-based service that takes a URL, captures a screenshot of the website, uploads it to an Amazon S3 bucket, and returns a public link to the screenshot. This repository includes both the infrastructure (Terraform) and the application logic (Python) required to deploy the service on AWS.:contentReference[oaicite:1]{index=1}

---

## 📌 Features

- 🖼️ Capture screenshots of any public URL
- ☁️ Upload and store screenshots in Amazon S3
- 📡 Expose endpoint to trigger screenshot generation
- 🔐 Infrastructure as Code using Terraform

---

## 🧠 Architecture

The solution consists of:

1. **Infrastructure** (Terraform):
   - EC2 instance (or optionally Lambda) that runs the screenshot service  
   - S3 bucket for screenshot storage  
   - Security groups and IAM roles for secure access

2. **Application Logic** (Python):
   - Python script that:
     - Takes a URL input
     - Renders and captures the screenshot
     - Uploads the image to the designated S3 bucket
     - Returns a URL to the stored screenshot:contentReference[oaicite:2]{index=2}

---

## 🔧 Prerequisites

Before you begin, make sure you have:

- An **AWS Account**
- AWS CLI configured with sufficient permissions
- Terraform (v1.0+)
- Python 3.7+
- Required Python packages (see below)

---
## 🛠️ Deployment

### 1. Clone the Repository

git clone https://github.com/theduolc/AWS-screenshot-gen.git
cd AWS-screenshot-gen

Initialize Terraform:
terraform init
terraform plan
terraform apply

Python Setup

pip install -r requirements.txt

Once deployed and the EC2 instance (or other compute) is running:

Send a POST request to your service endpoint with a JSON body:

{
  "url": "https://example.com"
}

Usage

+ Load the URL
+ Capture a screenshot
+ Upload it to the configured S3 bucket
+ Return the screenshot download link

Example:

curl -X POST https://<SERVICE_ENDPOINT> \
     -H "Content-Type: application/json" \
     -d '{"url":"https://example.com"}'


