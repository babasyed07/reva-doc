# GitHub Integration for Policy-as-Code Management

Reva’s Policy Administration Point (PAP) integrates with **GitHub** to automate and streamline policy lifecycle management. Policies authored in Reva are version-controlled in the linked GitHub repository, enabling:

- Collaborative editing  
- Audit trails via commits  
- Seamless promotion across environments (e.g., dev → prod)  

Reva's governance tools (e.g., approval workflows) work with GitHub’s pull requests for policy reviews, bridging **policy-as-code** practices with Reva’s centralized enforcement.

---

## Key Benefits

- **Version Control**: Track policy changes via Git history  
- **Collaboration**: Teams edit policies concurrently with merge controls  
- **Automation**: Sync policies to Reva for real-time enforcement  

---

## Prerequisites

### GitHub Repository Setup

- Create a repository to store policy files  
- Refer to [GitHub’s Creating a Repository documentation](https://docs.github.com/en/get-started/quickstart/create-a-repo)  

### Personal Access Token (PAT)

- Generate a **classic PAT** with `repo` scope (full control of private repositories)  
- Refer to [GitHub’s PAT Creation Guide](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)  

---

## Step-by-Step Integration Guide

### 1. Initiate GitHub Integration

- From Reva’s main menu, go to **Integrations** → click **+ Integration**  
- Select **GitHub** from the dropdown list  
- A configuration slider will appear from the right side of the screen  

---

### 2. Basic Information

- **Integration Name***: A unique name (e.g., `github-int`) to track the integration  
- **Description**: e.g., `"GitHub repo for policy management"`  

---

### 3. Authentication & Repository Details

- **Personal Access Token (PAT)**: e.g., `github_pat_xxx` (must have `repo` permissions)  
- **Email**: GitHub email linked to the PAT (e.g., `user@domain.com`)  
- **Username**: GitHub username (e.g., `johndoe`)  
- **Repository URL***: e.g., `https://github.com/username/repo.git`  

---

### 4. Branch Selection

- **Choose Branch**: Select the target branch (e.g., `main` or `dev`) where policies will be synced  

---

### 5. Activate Integration

- Click the **Activate** button (bottom-right corner) to complete the process  

---

