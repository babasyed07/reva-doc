**Integrations Overview: GitLab, GitHub, and Amazon Verified Permissions
(AVP)**

Reva's platform enables centralized policy management by integrating
with GitLab, GitHub, and Amazon Verified Permissions (AVP). These
integrations serve distinct purposes in the policy lifecycle: GitLab and
GitHub are used for distributing policies created in Reva via
version-controlled repositories, while the entire policy lifecycle in
AVP is fully managed by Reva. Reva acts as the central interface for
authoring, distributing, versioning, and auditing policies across all
three systems --- combining developer-friendly workflows with
cloud-scale policy enforcement.

**GitLab Integration**

Reva integrates with GitLab to streamline the distribution of policies
created within the Reva platform. Policies are stored in a
version-controlled GitLab repository, allowing teams to collaborate on
policy development and promote changes across environments using
established Git workflows.

**Key Features:**

a.  Distribution Only: GitLab is used for policy storage and versioning
    but does not participate in enforcement.

b.  Merge-Based Collaboration: Teams review and approve policy updates
    through GitLab Merge Requests.

c.  Change Tracking: All policy modifications are captured via Git
    commit history, supporting traceability and rollback.

d.  Automated Synchronization: Once approved, changes are automatically
    synced back to Reva for activation.

**GitHub Integration**

Reva's integration with GitHub functions similar to GitLab, offering a
Git-based workflow for policy distribution. Policies authored in Reva
are pushed to or pulled from a GitHub repository, enabling secure,
collaborative change management through Pull Requests.

**Key Features:**

a.  Distribution Only: GitHub serves as the version-controlled source of
    truth; it is not responsible for enforcement.

b.  Pull Request Workflow: Policy changes follow GitHub's PR review and
    approval process before deployment.

c.  Visibility and Auditing: Synced updates are logged in Reva and
    traceable through GitHub commit history.

d.  Continuous Sync: Merged changes are automatically reflected in
    Reva's internal policy store.

**Amazon Verified Permissions (AVP) Integration**

Reva's integration with Amazon Verified Permissions (AVP) enables
full-scale policy enforcement using AWS's Cedar-based policy engine.
Policies authored and versioned in Reva are synchronized to AVP's policy
store, where they are evaluated in real time to determine access
permissions.

**Key Features:**

a.  Complete Lifecycle Management: Reva creates, configures, and
    maintains AVP policy stores within AWS environments.

b.  Built-in Version Control: All policy updates are versioned and
    governed directly through Reva.

c.  Scalable Enforcement: AVP evaluates policies at runtime, delivering
    low-latency access decisions.

d.  Governance-Driven Management: Reva oversees policy drafting,
    approvals, deployment, and audit logging.

e.  Real-Time Auditing: AVP decision logs are ingested via AWS
    CloudTrail, giving administrators full visibility within Reva.
