# HCM Approvals – Management Hierarchy

## Objective

Configure **Management Hierarchy (Line Manager)** as the approval method for **New Hire Approvals**.

The objective is to ensure that a new hire transaction is routed to the employee's assigned **Line Manager** for approval.

---

## Configuration Summary

### 1. Create Test Users

Created the following test users:

* **SAIF AHMED**

  * Role: Human Resources Analyst
  * Used to initiate the Hire transaction.

* **MOHAMED SALAH**

  * Role: Human Resources Administrator
  * Used as the Line Manager/Approver.

### 2. Assign Line Manager

Assigned **MOHAMED SALAH** as the **Line Manager** for **SAIF AHMED**.

This establishes the management hierarchy used by the approval rule.

**Hierarchy:**

SAIF AHMED
↓
MOHAMED SALAH
↓
**Approver**

### 3. Create New Hire Approval Rule

Created a **New Hire Approval Rule** using:

**Approval Type:** Management Hierarchy
**Approver:** Line Manager

Configured a condition for:

**Worker Type:** Full-Time Regular

When the condition is met, the transaction is routed through the Management Hierarchy to the employee's Line Manager.

### 4. Configure Default Rule

Created a **Default Rule** to automatically approve transactions when the specific Full-Time Regular condition is **not met**.

This provides a fallback path and prevents transactions from remaining without an applicable approval rule.

### 5. Test the Approval Process

Created a test worker using the configured **Hire** flow.

The test transaction was submitted to validate the configured approval rule.

Expected flow:

**Hire Worker**
→ **Full-Time Regular condition evaluated**
→ **Management Hierarchy identified**
→ **MOHAMED SALAH identified as Line Manager**
→ **Approval request routed to MOHAMED SALAH**

### 6. Validate the Transaction

Validated the approval configuration using **Transaction Summary**.

Confirmed that the Hire transaction was evaluated against the configured approval rules and that the Management Hierarchy approval configuration was functioning as expected.

---

## Final Configuration

| Component       | Configuration        |
| --------------- | -------------------- |
| Transaction     | New Hire             |
| Approval Method | Management Hierarchy |
| Approver        | Line Manager         |
| Condition       | Full-Time Regular    |
| Test Initiator  | SAIF AHMED           |
| Test Approver   | MOHAMED SALAH        |
| Fallback Rule   | Auto Approve         |
| Validation      | Transaction Summary  |

## Result

The **New Hire Approval** process was successfully configured using **Management Hierarchy (Line Manager)**.

The test confirmed that the configured Line Manager is used as the approver when the **Full-Time Regular** condition is satisfied, while the Default Rule provides an automatic approval path when the condition is not met.
