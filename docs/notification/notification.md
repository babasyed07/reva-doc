# 🔔 **Notifications**

**Reva’s notification system** ensures transparent and traceable policy management by delivering **real-time alerts** throughout the **policy approval and activation process**. These notifications are especially important in collaborative environments where multiple users interact with shared policy stores.

When a user modifies a policy that is **owned or managed by someone else**, Reva automatically initiates an **Approval Workflow**. This process safeguards against **unauthorized or unintended changes**, upholding **governance and security standards**.

---

Users can access notifications by **clicking the Bell Icon** located in the **left sidebar** of the **main navigation menu**. This section offers a **chronological view** of key events, such as **policy updates**, **approvals**, and **rejections**. Each notification provides context with **timestamps**, **policy and application names**, and the **username** of the user involved—ensuring complete traceability.

---

## 🧭 **Notification States**

There are three key **notification states** in this workflow:

### 📨 **Sent For Approval**

This notification is triggered when a user **modifies a policy** they do not directly **own or manage**. The change is flagged and routed for approval, with the status marked as  
**“pending approval – Update.”**  

It includes:
- **Policy Name**
- **Application Name**
- **Initiator’s Username**
- **Timestamp**

This helps reviewers assess and respond to the update request.

---

### ✅ **Activated**

When a **policy update is approved** by the designated **owner or reviewer**, the system issues an **“Activated”** notification labeled  
**“on activate – Update.”**

It confirms:
- The **updated policy** is now in effect
- The **identity of the approver**

This provides visibility into who validated and activated the change.

---

### ❌ **Activation Rejected**

If the proposed update is **declined**, a **“Rejected”** notification is issued.  
This status means the **policy remains unchanged**.

It includes:
- **Who rejected** the change
- **When it occurred**

This enables the initiator to **revise the request** or seek **clarification** from the approver.
