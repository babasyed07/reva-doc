# 🛡️ **Policy Governance and Lifecycle Management**

## **Overview**

Reva provides a centralized platform for managing authorization policies across modern applications, environments, and integrations. At the heart of this system is a structured approach to policy governance and lifecycle management, enabling organizations to securely define, distribute, test, and audit access controls. The platform follows a hierarchical flow—starting from Category, progressing through Application and Environment, and culminating in a Policy Store, where the logic of who can access what, when, and under what conditions is precisely managed.

Reva natively supports Cedar, the declarative policy language developed by AWS for fine-grained access control. Cedar provides a human-readable yet expressive syntax for defining both policies and schemas. ByleveragingCedar, Reva enables organizations to model access decisions using standardized, extensible semantics—including role-based, attribute-based, and contextual access logic. This compatibility ensures seamless integration with services like Amazon Verified Permissions while supporting scalable, testable, and auditable policy management practices.

Reva supports both the creation of new policy stores and the integration of existing ones, such as Amazon Verified Permissions (AVP). When an existing AVP policy store is selected, schema and entity definitions are automatically imported if already definedin AVP. If a new store is created, users are guided through the manual configuration of schemas, entity types, policies, and test data. Throughout this process, Reva ensures traceability, visibility, and compliance via clearly defined lifecycle stages—from schema modeling and policy creation to runtime validation and historical versioning.

This document outlines the core components and functions within Reva's Policy Store—Insights, Policies, Test Data, Schema, and Version History—each of which plays a critical role in designing, governing, and auditing enterprise-level access control.

---

## **Reva Policy Store Onboarding & Lifecycle Flow**

### **Category**

A Category acts as the top-level grouping used to organize applications by business domain, regulatory requirement, or organizational structure (e.g., “Healthcare”,“Finance”,“Internal Tools”). This helpsadministrators'segment and manage large sets of applications in a logical, scalable way. Policies, environments, and configurations inherit context from their category.

### **Application**

Anapplicationrepresentsa single system or service being onboarded within Reva. Each application is registered under a category and can have one or more associated environments (like Development, QA, Production). Applications are the central unit around which access policies are managed andmonitored.

### **Environment**

An Environment defines the deployment context for an application (e.g., Dev, QA, Staging, Prod). This allows teams to enforce different access rules in different operational stages. Each environment is connected to a Policy Store which contains the access model, rules, and enforcement logic specific to that environment.

### **Existing Policy Store (Auto-Populated)**

If the user selects an existing AVP (Amazon Verified Permissions) Policy Store, Reva will automatically fetch and populate the associated schema and entity types. This is ideal when a policy model has already been established in AVP and needs to be integrated into Reva for governance, visibility, and testing. Auto-population minimizes manual errors and accelerates onboarding.

### **New Policy Store (Manual Setup)**

If no pre-existing policy store exists, users can create a New Policy Store in Reva. This requires manual definition of the policy,schema (e.g., who can do what on which resources), entity types, and attribute mappings. It also involves configuring the test data and hierarchy and optionally integrating with external systems like GitHub/GitLab for policy distribution.

---

## **Policy Store Configuration**

Reva’s application onboarding and policy configuration process follows a structured, hierarchical flow to ensure logical separation, clarity, and security across environments. 

To begin configuring or managing access policies in Reva, follow the structured path through the main interface: 

  a. Go to “Application” in the main navigation menu.  
     *This opens the interface where all registered applications are organized under their respective categories.*

  b. Select a Category, such as Retail.  
     *Categories help segment applications by business function or operational context.*

  c. Choose the specific Application you want to manage.  
     *Applications represent the systems or services that require access control.*

  d. Select the Environment (e.g., Dev, QA, or Prod) under the application.  
     *Each environment has its own policies and may differ in terms of users and access needs.*

  e. Click on the associated Policy Store for that environment.  
     *It will now be directed to the policy management interface where you can define schema, configure policies, upload test data, and view history.*

---

## **Insights**

The Insights tab in Reva serves as a dynamic dashboard for monitoring the health and operational activity of a policy store. It consolidates real-time and historical information to help teams track configuration progress, identify pending tasks, and quickly assess policy status across environments. 

  a. Top Activity provides a chronological log of recent actions such as policy activations, imports, or failures along with status indicators (e.g., Completed, Failed) and timestamps. This helps identify who performed what actions and whether any issues occurred during critical events like importing external policies. 

  b. Pending Actions highlights tasks that require follow-up or completion, ensuring teams don’t overlook necessary steps to finalize the policy setup. If no actions are pending, the interface clearly communicates that the store is in a stable state. 

  c. Application Snapshot offers an overview of key statistics (such as policy count, test case results, and mapped schema entities) and may be used for further drilldowns or contextual reporting. 

  d. Version History timeline, which visually maps all configuration events across a 24-hour cycle. Each entry is tagged with its version number and timestamp, giving teams a clear and audit-friendly view of how the policy store has evolved over time. This tight integration of current activity and version history ensures both visibility and traceability, helping organizations maintain governance while confidently iterating on access control models. 

---

## **Policies**

The Policies tab is where all access rules are defined, viewed, and managed. It presents policies in a tabular format that allows easy sorting, filtering, and editing. Each policy defines which Principal (user or role) can perform which Action (like view or edit) on which Resource (such as Patient or Record). Every policy also includes an Effect (Allow or Deny) and an optional Description for better context and documentation.

| **Column Name**  | **Description** |
|------------------|-----------------|
| **Policy Name**  | The unique name or identifier assigned to each policy rule. It helps in referencing and auditing specific access logic. |
| **Principal**    | The user, role, or system entity (e.g., doctor, admin) that initiates the action defined in the policy. |
| **Action**       | The operation the principal intends to perform (e.g., viewPatient, editConcept). |
| **Resource**     | The target object on which the action is performed (e.g., Patient, Encounter, Form). |
| **Effect**       | Specifies whether the action is Allowed or Denied by the policy. |
| **Description**  | An optional text field used to describe the business logic or intent behind the policy. Helpful for collaboration and reviews. |
| **Created By**   | Displays the user who created the policy for accountability and traceability. |
| **Last Updated** | Timestamp of the most recent change made to the policy. Useful for audits and version tracking. |
| **Actions**      | Provides buttons or icons to edit, delete, or view details of the policy. |

Alongside the tabular list, a powerful Visual Access Map is provided, offering a graphical representation of defined access relationships. This map visually connects Principals → Actions → Resources and helps quicklyidentifymissing mappings, redundant rules, or potential over-permissioning. Together, the tabular and visual views make it easy for both technical and non-technical users to understand,maintain, andvalidatepolicy logic.

To create a policy in Reva, follow the below mentioned steps:

  a. Click "Create Policy"Launches the policy creation form.    
     Launches the policy creation form.

  b. **Enter the Policy Name  
     Provide a clear, descriptive name for the policy (e.g.,AllowDoctorsToViewPatients).

  c. **Select the Principal  
     Choose a user, role, or system identity (e.g., Doctor, Admin).

  d. **Select the Action   
     Choose the operation the principal will perform (e.g.,viewPatient,editConcept).

  e. **Select the Resource   
     Define the object the action applies to (e.g., Patient, Form, Encounter).

  f. **Set the Effect   
     Choose whether to “Allow” or “Deny” this action.

  g. **(Optional) Add a Description   
     Explain the purpose or context of the policy for easier review and collaboration.

  h. Click "Save"  
     The policy will appear in the table and be reflected in the Access Map.

💡 Tip: After saving, use the Visual Access Map to ensure complete coverage and logical correctness across all access relationships.

---

## **Schema**

The Schema tab defines the foundational access model used throughout the policy store. This includes creating the core entities: Principals (e.g., User, Doctor), Actions (e.g.,viewPatient,updateConcept), and Resources (e.g., Patient, Encounter). These components act as the building blocks for policies and must be defined before any rule can be authored.

Each of these entities can be extended with attributes—such as role, department, orownerId—that allow for more granular, context-aware access control decisions. This makes the policy model flexible and powerful, enabling attribute-based access control (ABAC). The Schema tab also supports entity hierarchies, where permissions can be grouped or inherited, simplifying rule definitions and supporting scalable governance.

Ultimately, theschemadetermineswhat can be expressed in policy logic, making it the cornerstone of Reva’s access control architecture.

To create a Schema in Reva, follow the below mentioned steps:

  a. Click "Add Principal"  
     Define the users or roles that willinitiateactions (e.g., User, Admin, Doctor).

  b. Add Attributes (Optional)  
     Attach metadata to the principal (e.g.,userId, role, department). This supports fine-grained filtering.

  c. Click "Add Action"  
     Define actions likeviewPatient,editConcept, ordeleteRecordthat principals can perform.

  d. Click "Add Resource"  
     List the objects targeted by actions (e.g., Patient, Form, Location).

  e. Attach Attributes to Resources (Optional)  
     Add contextual attributes likeownerId, type, or status.

  f. Setup Hierarchy (Optional)  
     Establish relationshipssuch asedit and view under a parent manageaction, ordefine parent-child relationships between resources.

  g. Click "Save and Activate"  
     Finalize the schema. Once activated, it becomes available for use in the Policies tab.

💡 You cannot create policies until all necessary schema components (Principal, Action, Resource) are defined and activated.

---

## **Test Data**

The Test Data tab enables scenario-based, practical validation of access control decisions. It allows users to upload simulated authorization requests through datasets, typically in CSV format, often zipped together. These datasetsrepresentreal-world access scenarios, such as:

Example: “Doctor John attempts to view Patient Jane at 3 PM from a mobile device.”

Once uploaded, each test case is evaluated against all active policies, and the actual decision (Allow or Deny) is compared against the expected outcome. This makes the Test Data tab a vital part of the validation lifecycle, helping teams confirm that policies work as intended and do not result in over-permissioned or denied access where itshouldn'tbe.

💡 Template: A sample test data template is downloadable directly from the interface and available in CSV format. It includes pre-defined headers and example rows to guide users in structuring their own test cases correctly.

To create a Test Data in Reva, follow the below mentioned steps:

  a. Click "Upload Test Data"  
     Select a .zip filecontainingyour test cases, ideally structured in CSV format.

  b. Review Uploaded Data  
     Check the structure and contents of the uploaded file to ensure the data reflects real-world access scenarios (e.g., user roles, actions, time-based conditions).

  e. Define Test Case Conditions  
     Map the test data fields to the appropriate entities defined in the Schema (e.g., mapping user IDs to Principals, actions to Action types, etc.).

  f. Run the Test  
     Click "Run Test" to evaluate the uploaded data against your active policies.

  g. Review Results  
     Examine the outcomes. The platform will display whether the access attempts were allowed or denied, based on your policy configurations. You can also view discrepancies between the expected and actual results.

  h. Adjust Policies (if necessary)  
     If the test results highlight issues, you can revise the policies or schema and re-upload the test data to verify corrections.

  i. Save Test Results  
     Once satisfied with the test results, save your test case scenarios for future reference or auditing.

💡**Template:**template is downloadable and available in CSV format.

💡**Best Practice:**Regularly run test data after making changes to policies or schemas to ensure no unintended access is granted or revoked.

---

## **Version History**

The Version History tab provides a comprehensive audit log and version control system for the entire policy store. Every significant configuration change—whetherit'sa schema update, policy modification, or test data execution—is automatically recorded with a timestamp, the author of the change, anda short descriptionof the action. This helps teams quicklyidentifywhathaschanged, when it occurred, and by whom, ensuring full transparency across collaborative teams.

In addition to being a historical record, the Version History tab supports version comparisons, allowing users to view differences between configurations over time. Where supported, users can also roll back toa previousversion if a change causes unexpected behavior or breaks access logic. This capability is essential for ensuring operational resilience and rapid recovery.

For organizationsoperatingin regulated industries, Version History acts as formal evidence of governance. It provides a secure, traceable, and tamper-proof record of all authorization-related changes, helpingmaintainaudit readiness and ensuring accountability at every stage of the policy lifecycle.