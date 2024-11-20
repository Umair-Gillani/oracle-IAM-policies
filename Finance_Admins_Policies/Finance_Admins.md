### Finance_Admins_Tested_Running_Policies :

```plaintext
define tenancy usage-report as ocid1.tenancy.oc1..aaaaaaaxxxxxxx
endorse group 'Default'/'FinanceAdmins' to read objects in tenancy usage-report
Allow group 'Default'/'FinanceAdmins' to manage accountmanagement-family in tenancy
Allow group 'Default'/'FinanceAdmins' to manage tickets in tenancy
Allow group 'Default'/'FinanceAdmins' to manage usage-budgets in tenancy
Allow group 'Default'/'FinanceAdmins' to read usage-reports in tenancy
Allow group 'Default'/'FinanceAdmins' to read audit-events in tenancy
Allow group 'Default'/'FinanceAdmins' to inspect tag-namespaces in tenancy
Allow group 'Default'/'FinanceAdmins' to read quotas in tenancy
```

---

To verify the **FinanceAdmins policies**, follow these **step-by-step tests** through the Oracle Cloud Infrastructure (OCI) Console. Each step includes the relevant policy, the actions to verify, and what you should expect.

---

### **1. Usage Report Access**
#### Policies to Verify:
```plaintext
define tenancy usage-report as ocid1.tenancy.oc1..aaaaaaaxxxxxxx
endorse group 'Default'/'FinanceAdmins' to read objects in tenancy usage-report
Allow group 'Default'/'FinanceAdmins' to read usage-reports in tenancy
```
#### Steps:
1. Navigate to:
   ```
   Governance & Administration > Usage Reports
   ```
2. **Verify**:
   - Ensure you can:
     - View and list usage reports available in the tenancy.
     - Download the usage reports (e.g., CSV files).
   - **Check Object Access**:
     - Navigate to **Object Storage > Buckets**.
     - Open the `usage-report` bucket (defined in the policy) and ensure you can view and download its objects.

---

### **2. Account Management**
#### Policies to Verify:
```plaintext
Allow group 'Default'/'FinanceAdmins' to manage accountmanagement-family in tenancy
```
#### Steps:
1. Navigate to:
   ```
   Governance & Administration > Cloud Advisor
   ```
2. **Verify**:
   - Ensure you can:
     - View and manage organization details (e.g., subscriptions, billing units).
     - Access account settings and update configurations.

---

### **3. Ticket Management**
#### Policies to Verify:
```plaintext
Allow group 'Default'/'FinanceAdmins' to manage tickets in tenancy
```
#### Steps:
1. Navigate to:
   ```
   Help > Support Tickets
   ```
2. **Verify**:
   - Ensure you can:
     - View and create support tickets.
     - Update existing tickets (e.g., add comments or close tickets).

---

### **4. Budget Management**
#### Policies to Verify:
```plaintext
Allow group 'Default'/'FinanceAdmins' to manage usage-budgets in tenancy
```
#### Steps:
1. Navigate to:
   ```
   Governance & Administration > Budgets
   ```
2. **Verify**:
   - Ensure you can:
     - Create new budgets.
     - View, edit, and delete existing budgets.
     - Set alerts for budgets to monitor spending.

---

### **5. Audit Events**
#### Policies to Verify:
```plaintext
Allow group 'Default'/'FinanceAdmins' to read audit-events in tenancy
```
#### Steps:
1. Navigate to:
   ```
   Identity & Security > Audit
   ```
2. **Verify**:
   - Ensure you can:
     - View audit logs for actions performed in the tenancy, such as budget creation or usage report downloads.
     - Filter logs by compartments or resource types.

---

### **6. Tag Namespace Inspection**
#### Policies to Verify:
```plaintext
Allow group 'Default'/'FinanceAdmins' to inspect tag-namespaces in tenancy
```
#### Steps:
1. Navigate to:
   ```
   Governance & Administration > Tag Namespaces
   ```
2. **Verify**:
   - Ensure you can:
     - List all tag namespaces in the tenancy.
     - View details of each tag namespace.

---

### **7. Quota Inspection**
#### Policies to Verify:
```plaintext
Allow group 'Default'/'FinanceAdmins' to read quotas in tenancy
```
#### Steps:
1. Navigate to:
   ```
   Governance & Administration > Limits, Quotas, and Usage
   ```
2. **Verify**:
   - Ensure you can:
     - View quotas for resources (e.g., compute, storage, and networking limits).
     - Inspect usage against these quotas.

---

### **Full Policy Set Summary**
Here’s the complete and validated policy set for `FinanceAdmins`:

```plaintext
define tenancy usage-report as ocid1.tenancy.oc1..aaaaaaaxxxxxxx
endorse group 'Default'/'FinanceAdmins' to read objects in tenancy usage-report
Allow group 'Default'/'FinanceAdmins' to manage accountmanagement-family in tenancy
Allow group 'Default'/'FinanceAdmins' to manage tickets in tenancy
Allow group 'Default'/'FinanceAdmins' to manage usage-budgets in tenancy
Allow group 'Default'/'FinanceAdmins' to read usage-reports in tenancy
Allow group 'Default'/'FinanceAdmins' to read audit-events in tenancy
Allow group 'Default'/'FinanceAdmins' to inspect tag-namespaces in tenancy
Allow group 'Default'/'FinanceAdmins' to read quotas in tenancy
```

---

### **How to Confirm Each Policy**
1. **Usage Reports**:
   - Check access to **Governance & Administration > Usage Reports**.
   - Confirm object access in the **Object Storage > Buckets > usage-report** bucket.

2. **Account Management**:
   - Navigate to **Account Management** and check access to subscription and billing settings.

3. **Tickets**:
   - Test creating, updating, and closing support tickets.

4. **Budgets**:
   - Test creating and managing budgets, including setting up alerts.

5. **Audit Events**:
   - Check access to audit logs and ensure visibility into finance-related operations.

6. **Tag Namespaces**:
   - Confirm you can list and inspect tag namespaces.

7. **Quotas**:
   - Test viewing service quotas and usage under **Limits, Quotas, and Usage**.

---

### **Expected Outcome**
- Users in the `FinanceAdmins` group should be able to perform the listed actions without encountering "Authorization Failed" or "Resource Not Found" errors.
- If any permissions fail:
  - Verify that the user is part of the `FinanceAdmins` group.
  - Double-check policy syntax and wait for propagation.

Let me know if you encounter any issues!