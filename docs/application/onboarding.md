# **Application Onboarding**

## **Overview**

**Application Onboarding** is a structured process designed to register, configure, and prepare applications for secure deployment within an organization’s infrastructure. It ensures that each application is properly identified, categorized, linked to its operational environments, and governed by appropriate security policies before it becomes operational.

The process begins with the collection of **essential application metadata**, such as the **Application Name**, its **Business Category**, **Ownership**, and a **high-level description** of its purpose. This foundational information helps ensure consistent management, reporting, and compliance alignment across the organization.

Once the basic information is provided, the next step involves associating the application with one or more **environments** — such as **Development**, **Staging**, or **Production** — where it will be deployed. Each environment is then linked to a **Policy Store**, which defines the **access control model** governing who can do what with the application’s data and resources.

Within the **Policy Store**, administrators define the **Policy Schema**, which consists of three core components:

- **Principals** (e.g., users or systems requesting access)
- **Actions** (e.g., create, read, update operations)
- **Resources** (e.g., data entities like Patient, Concept, or Document)

This schema outlines the structure of **authorization and access control rules**. It can be created manually using a **visual mapping interface** or imported via **predefined templates or schema files**. The schema is enriched by defining **static attributes** (e.g., **User ID**, **Department**) and **runtime attributes** (e.g., **Access Time**, **Location**), which help enforce **context-aware access policies**. A logical hierarchy of entities and actions is also established to support **policy inheritance** and reduce redundancy.

After completing the schema definition, the **Policy Store** is activated, and the onboarding process moves to **uploading test data**. This test data simulates real-world interactions with the application, validating that the access policies behave as expected under various scenarios.

Finally, once all steps are completed — including **policy configuration** and **test data upload** — the application is fully onboarded and ready for integration into operational workflows. This structured onboarding process not only enforces security from the start but also lays the groundwork for **scalable**, **auditable**, and **compliant application lifecycle management**.

---

## **Onboarding Landing Page Columns**

| **Column Title** | **Explanation** |
|------------------|-----------------|
| **Name** | Displays the name of the onboarded application. |
| **Category** | Indicates the business or technical domain of the application (e.g., Hospital, Insurance, Enterprise). |
| **Owner** | Shows the user responsible for managing the application. |
| **Progress** | Provides the current onboarding step or pending action. |
| **Status** | Reflects the application’s overall onboarding completion state (e.g., In Progress, Completed). |
| **Last Updated** | Shows the most recent date and time when the application details were modified. |
| **Action** | Allows the user to perform management actions such as deleting the application. |

---

## **Step-by-Step Application Onboarding Process**

### **Basic Application Information**

- **Enter the Application Name** (e.g., `OpenMRS`)  
  _This is the application name used to register the application._

- **Select the Environment(s)** where the application will be used  
  _Choose environments like Development, QA, or Production._

- **Choose the Category** of the application (e.g., `Healthcare`, `Internal`)  
  _Helps in grouping and reporting based on domain._

- **Add Application Tags** (e.g., `critical`, `external`)  
  _Tags assist in quick filtering and identification._

- **Assign Application Owner(s)**  
  _Owners are accountable for managing the application._

- **Write a Description** summarizing the application’s purpose  
  _Provides a quick overview of the application._

---

### **Configuring the Environment, Defining the Policy Store, and Linking the Integration**

#### **Click Add Environment**  
_Start adding a new environment to associate specific infrastructure details._

#### **Create a New Environment**

- **Enter the Environment Name** (e.g., `Prod`)  
  _Use a meaningful name like `Development`, `QA`, or `Production`._

- **Choose an existing Policy Store** or **Create a New Policy Store**  
  _Click on **+ Policy Store** in the top right if needed._

---

### **If Creating a New Policy Store:**

- **Enter a Display Name** (e.g., `eMRS-PolicyStore`)  
  _Uniquely identifies your Policy Store._

- **Write a Description** explaining its purpose  
  _E.g., managing healthcare access rules._

- **Select a Policy Store Type** (e.g., `AVP`)

- **Choose the appropriate Integration** from the dropdown  
  _E.g., link with Git for version control._

- **Review Added Environment(s)**  
  - Confirm the **Environment Name**
  - Confirm the **Policy Store Name**

- **Click Create** to proceed

---

### **If Choosing an Existing Policy Store:**

- **Confirm the selected Policy Store** (tick box)
- **Ensure Policy Store Name and Integration Details are correct**
- **Click Create the Environment**

---

### **Configure the Policy Store**

#### **Start Configuration**

- **Check Configuration Status**: `Awaiting Configuration`  
- **Click the Gear Icon** to begin schema configuration

---

### **Option 1: Define Policy Structure Manually**

Manually map:

- **Principal**: Who is requesting access (e.g., `User`)
- **Action**: What they want to do (e.g., `createPatient`, `viewPatient`)
- **Resource**: What they want to access (e.g., `Patient`, `Concept`)

---

### **Option 2: Add from Library or Upload Existing Schema**

- **Add from Library**: Choose from prebuilt templates  
- **Upload Existing Schema**: Upload a JSON schema file

- **Click on Preview** to view the mapping
- **Click Next** to define attributes

---

### **Define Attributes for Entity Types**

- **Click Next**  
- Configure **static attributes** like **User ID**, **Email**, **Username**

---

### **Add Run Time Attributes**

- **Click Next**  
- Add **dynamic attributes** like **Current Time**, **Access Location**

---

### **Setup Hierarchy**

- **Click Next**  
- Arrange **Entity Types** and **Actions** in a logical structure

---

### **Save and Activate the Policy Store**

- **Click "Save and Activate"** to finalize configuration

---

### **Proceed After Activating the Policy Store**

- Confirm that **Status** is `Active`
- **Click "Continue"** (top-right corner)

---

### **Upload Test Data Files**

- **Upload sample ZIP files** (JSON or CSV of users, roles, permissions)
- Drag and drop or **browse to upload**
- Confirm successful upload

---

### **Review Applications List**

- Navigate to **Manage Applications**
- View all registered apps and their **owners** and **categories**
- Review **Progress** and **Status** columns
