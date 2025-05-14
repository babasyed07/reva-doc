# GitLab Integration for Policy-as-Code Management in Reva

Reva integrates with **GitLab** to streamline the distribution of policies created within the Reva platform. Policies are stored in a version-controlled GitLab repository, allowing teams to:

- Collaborate on policy development  
- Promote changes across environments using Git workflows  

---

## Key Benefits

- **Distribution Only**: GitLab is used for policy storage and versioning but does not participate in policy enforcement  
- **Merge-Based Collaboration**: Teams review and approve policy updates through GitLab Merge Requests  
- **Change Tracking**: All policy modifications are captured via Git commit history  
- **Automated Synchronization**: Once approved, changes are automatically synced back to Reva for activation  

---

## Prerequisites

### GitLab Repository Setup

- Store your policy files in a GitLab repository  
- Refer to [GitLab’s Repository Creation Guide](https://docs.gitlab.com/ee/user/project/repository/)  

### Personal Access Token (PAT)

- Generate a **PAT** with the following scopes:  
  - `api`  
  - `write_repository`  
- Refer to [GitLab’s PAT Guide](https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html)  

---

## Step-by-Step Integration Guide

### 1. Initiate GitLab Integration

- From Reva’s main menu, go to **Integrations** → click **+ Integration**  
- Select **GitLab** from the list of supported integrations  
- A configuration slider will appear from the right side of the screen  

---

### 2. Basic Information

- **Integration Name***: A unique identifier (e.g., `gitlab-pac`)  
- **Description**: Brief description (e.g., `"Policy-as-Code management"`)  

---

### 3. Authentication & Repository Details

- **Personal Access Token (PAT)**: e.g., `gipat-xxxx`  
- **Email**: GitLab account email (e.g., `user@domain.com`)  
- **Username**: GitLab username (e.g., `dev-user`)  
- **Repository URL***: e.g., `https://gitlab.com/user/repo.git`  
  - Must start with `https://` and end with `.git`  

---

### 4. Branch Selection

- **Choose Branch**: Select the branch (e.g., `main`) where policies should be synced  

---

### 5. Activate Integration

- Click the **Activate** button (bottom-right corner) to complete the integration  
