# Integrations Overview: GitLab, GitHub, and Amazon Verified Permissions (AVP)

Reva’s platform enables **centralized policy management** by integrating with **GitLab**, **GitHub**, and **Amazon Verified Permissions (AVP)**. Each integration supports a different phase of the policy lifecycle:

- **GitLab and GitHub**: Used for distributing policies authored in Reva via version-controlled repositories.  
- **AVP**: Used for real-time policy enforcement with full lifecycle management from within Reva.

These integrations allow Reva to combine **developer-friendly workflows** with **cloud-scale policy enforcement**.

---

## 🔁 GitLab Integration

Reva integrates with **GitLab** to distribute policies through a Git-based workflow.

### ✅ Key Features

- **Distribution Only**: GitLab is used for storage/versioning, not enforcement.  
- **Merge-Based Collaboration**: Teams collaborate using GitLab Merge Requests.  
- **Change Tracking**: Policy changes are logged in Git history.  
- **Automated Synchronization**: Approved changes sync back to Reva automatically.

---

## 🔁 GitHub Integration

Reva’s **GitHub integration** provides similar functionality using GitHub as the repository backend.

### ✅ Key Features

- **Distribution Only**: GitHub acts as the source of truth for policy versions.  
- **Pull Request Workflow**: Policy changes follow PR-based review and merge.  
- **Visibility and Auditing**: All changes are traceable via GitHub commits.  
- **Continuous Sync**: Merged PRs automatically update Reva's policy store.

---

## ⚙️ Amazon Verified Permissions (AVP) Integration

Reva’s AVP integration provides **real-time enforcement** of access policies using AWS’s **Cedar** policy engine.

### ✅ Key Features

- **Complete Lifecycle Management**: Reva manages creation, configuration, and updates of AVP policy stores.  
- **Built-in Version Control**: All changes are governed through Reva's interface.  
- **Scalable Enforcement**: AVP delivers low-latency runtime policy evaluations.  
- **Governance-Driven Management**: Drafting, approval, and auditing handled centrally in Reva.  
- **Real-Time Auditing**: AVP decision logs are captured via AWS CloudTrail and displayed in Reva.

---

## 🚀 Summary

| Integration | Purpose               | Workflow Style       | Reva Role          | Enforcement |
|-------------|------------------------|------------------------|---------------------|--------------|
| GitLab      | Policy Distribution     | Merge Requests         | Sync and Visibility | ❌           |
| GitHub      | Policy Distribution     | Pull Requests          | Sync and Visibility | ❌           |
| AVP         | Enforcement & Governance| Real-time Evaluation   | Full Lifecycle      | ✅           |
