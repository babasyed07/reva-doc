# Amazon Verified Permissions (AVP) Integration

Reva’s Policy Administration Point (PAP) integrates with **Amazon Verified Permissions (AVP)** to centralize policy authoring, testing, and enforcement. Policies created in Reva are synchronized with AVP’s Cedar-based policy store, enabling:

- **Governance**: Approval workflows and version control for policy changes.  
- **Real-Time Enforcement**: AVP evaluates access requests using Reva-managed policies.  
- **Auditability**: Decision logs and policy history tracked in AWS CloudTrail.  

---

## Key Benefits

- **Consistency**: Policies authored in Reva are enforced by AVP across all applications.  
- **Scalability**: AVP’s serverless architecture handles high-volume authorization requests.  

---

## Prerequisites for AVP Integration

The user running the CloudFormation Template (CFT) must have broad permissions across the following AWS services:

- **CloudFormation** – to deploy the infrastructure  
- **IAM** – to create roles and policies for Reva  
- **CloudTrail and S3** – to capture and store audit logs  
- **EventBridge** – to route log events  
- **SQS** – to store events temporarily for Reva to consume  
- **AVP** – to allow Reva full access to the policy store (depending on the AVP setup)  

---

## Step-by-Step Integration Guide

### 1. Initiate AWS Integration

- From Reva's main menu, navigate to **Integrations** and click **+ Integration**  
- Select **AWS** from the list of supported integrations  
- A configuration slider will appear from the right side of the screen  

---

### 2. Basic Information

- **Integration Name**: e.g., `Amazon Verified Permission Onboarding`  
- **AWS Account Number**: e.g., `214899999999999`  
- **Description**: e.g., `"This is the onboarding of Amazon Verified Permission."`  
- **AWS Region**: e.g., `US East (N. Virginia)`  
- **Policy Type**: Select **AVP**  

---

### 3. Choose Permissions

#### Select Permission Level

- **Read/Write**:  
  - Reva manages AVP policy stores  
  - Full access to AVP services  
  - Read access to logs of AVP events  

- **Read**:  
  - Reva reads AVP policy stores for visualization and versioning  
  - Policy management is handled via the AWS AVP Console  
  - Read access to AVP event logs  

---

### 4. Save Configuration in Draft State

- Click **Save as Draft** to review and finalize the configuration before running the CloudFormation Template (CFT)  

---

### 5. Run CloudFormation Template (CFT)

#### Provide Account Information

- **AWS Account Number**: e.g., `2148999999999999`  
- **Region**: e.g., `us-east-1`  
- **Permission Level**: Choose Read or Read/Write  

#### Run the CFT

- Download and run the CFT in your AWS account and region  

The CloudFormation Template will:

1. Create an IAM role for Reva to access AVP and CloudTrail logs  
2. Create a CloudTrail and S3 bucket for log storage  
3. Create an EventBridge and SQS to push CloudTrail logs to Reva  
4. Grant full access permissions to AVP  
5. Provide read access to SQS  

#### Confirmation

- After running the CFT, check the confirmation box to indicate it was executed successfully  

---

### 6. Activate the Integration

- Click the **Activation** button to finalize the integration  
- The AWS account is now onboarded to the Reva Platform  
- The integration state will change from **Draft** to **Enabled**, indicating the connection is live and operational  

---

