Below is the **filtered and cleaned-up list of policies** for the `StorageAdmins` group after removing duplicates and ensuring they align with **OCI industry standards** and **SAMA compliance**:

---

### **Filtered Policies for StorageAdmins**

#### 1. **Volume Management**
```plaintext
Allow group 'Default'/'StorageAdmins' to manage volumes in tenancy
Allow group 'Default'/'StorageAdmins' to inspect volumes in tenancy
Allow group 'Default'/'StorageAdmins' to manage volume-groups in tenancy
Allow group 'Default'/'StorageAdmins' to inspect volume-groups in tenancy
Allow group 'Default'/'StorageAdmins' to manage volume-group-backups in tenancy
Allow group 'Default'/'StorageAdmins' to manage volume-backups in tenancy
Allow group 'Default'/'StorageAdmins' to read volume-backups in tenancy
Allow group 'Default'/'StorageAdmins' to use volume-backups in tenancy where request.permission='VOLUME_BACKUP_COPY'
Allow group 'Default'/'StorageAdmins' to manage boot-volume-backups in tenancy
Allow group 'Default'/'StorageAdmins' to use boot-volume-backups in tenancy where request.permission='BOOT_VOLUME_BACKUP_COPY'
```
*Grants full control over volumes, backups, volume groups, and associated resources, including copying backups.*

---

#### 2. **Instance Attachments**
```plaintext
Allow group 'Default'/'StorageAdmins' to inspect volume-attachments in tenancy
Allow group 'Default'/'StorageAdmins' to inspect instances in tenancy
Allow group 'Default'/'StorageAdmins' to use instance-family in tenancy
```
*Provides permissions to inspect instances and volume attachments for managing storage operations effectively.*

---

#### 3. **Backup Policies**
```plaintext
Allow group 'Default'/'StorageAdmins' to manage backup-policies in tenancy
Allow group 'Default'/'StorageAdmins' to manage backup-policy-assignments in tenancy
```
*Allows creation and assignment of automated backup policies for block volumes.*

---

#### 4. **File Storage Management**
```plaintext
Allow group 'Default'/'StorageAdmins' to manage file-family in tenancy
Allow group 'Default'/'StorageAdmins' to manage file-systems in tenancy
Allow group 'Default'/'StorageAdmins' to read mount-targets in tenancy
```
*Grants control over file systems and related resources like mount targets.*

---

#### 5. **Object Storage Management**
```plaintext
Allow group 'Default'/'StorageAdmins' to manage buckets in tenancy
Allow group 'Default'/'StorageAdmins' to manage objects in tenancy
Allow group 'Default'/'StorageAdmins' to manage objects in tenancy where any {request.permission='OBJECT_CREATE', request.permission='OBJECT_INSPECT'}
Allow group 'Default'/'StorageAdmins' to read buckets in tenancy
Allow group 'Default'/'StorageAdmins' to read objects in tenancy
```
*Enables full management of object storage buckets and objects, including read and write access.*

---

### **Final Summary of Policies**

Here is the consolidated list of policies for the `StorageAdmins` group:

```plaintext
Allow group 'Default'/'StorageAdmins' to manage volumes in tenancy
Allow group 'Default'/'StorageAdmins' to inspect volumes in tenancy
Allow group 'Default'/'StorageAdmins' to manage volume-groups in tenancy
Allow group 'Default'/'StorageAdmins' to inspect volume-groups in tenancy
Allow group 'Default'/'StorageAdmins' to manage volume-group-backups in tenancy
Allow group 'Default'/'StorageAdmins' to manage volume-backups in tenancy
Allow group 'Default'/'StorageAdmins' to read volume-backups in tenancy
Allow group 'Default'/'StorageAdmins' to use volume-backups in tenancy where request.permission='VOLUME_BACKUP_COPY'
Allow group 'Default'/'StorageAdmins' to manage boot-volume-backups in tenancy
Allow group 'Default'/'StorageAdmins' to use boot-volume-backups in tenancy where request.permission='BOOT_VOLUME_BACKUP_COPY'
Allow group 'Default'/'StorageAdmins' to inspect volume-attachments in tenancy
Allow group 'Default'/'StorageAdmins' to inspect instances in tenancy
Allow group 'Default'/'StorageAdmins' to use instance-family in tenancy
Allow group 'Default'/'StorageAdmins' to manage backup-policies in tenancy
Allow group 'Default'/'StorageAdmins' to manage backup-policy-assignments in tenancy
Allow group 'Default'/'StorageAdmins' to manage file-family in tenancy
Allow group 'Default'/'StorageAdmins' to manage file-systems in tenancy
Allow group 'Default'/'StorageAdmins' to read mount-targets in tenancy
Allow group 'Default'/'StorageAdmins' to manage buckets in tenancy
Allow group 'Default'/'StorageAdmins' to manage objects in tenancy
Allow group 'Default'/'StorageAdmins' to manage objects in tenancy where any {request.permission='OBJECT_CREATE', request.permission='OBJECT_INSPECT'}
Allow group 'Default'/'StorageAdmins' to read buckets in tenancy
Allow group 'Default'/'StorageAdmins' to read objects in tenancy
```

--- 
\.
\.
\.
### *###############################################################################*

### *###############################################################################*

### *###############################################################################*
\.
\.
\.

---


To confirm that all the policies for the `StorageAdmins` group are working as intended, you can follow these **step-by-step tests** through the OCI Console. Each step includes the relevant policy, the actions to verify, and what you should expect.

---

### **1. Volume Management**
#### Policies to Verify:
```plaintext
Allow group 'Default'/'StorageAdmins' to manage volumes in tenancy
Allow group 'Default'/'StorageAdmins' to inspect volumes in tenancy
```
#### Steps:
1. Navigate to:
   ```
   Storage > Block Volumes
   ```
2. **Verify**:
   - Ensure you can:
     - List all block volumes (for `inspect volumes`).
     - Create a new volume, update, and delete existing volumes (for `manage volumes`).

---

### **2. Volume Groups**
#### Policies to Verify:
```plaintext
Allow group 'Default'/'StorageAdmins' to manage volume-groups in tenancy
Allow group 'Default'/'StorageAdmins' to inspect volume-groups in tenancy
```
#### Steps:
1. Navigate to:
   ```
   Storage > Block Volumes > Volume Groups
   ```
2. **Verify**:
   - Ensure you can:
     - List all volume groups (for `inspect volume-groups`).
     - Create, update, and delete volume groups (for `manage volume-groups`).

---

### **3. Volume Backups**
#### Policies to Verify:
```plaintext
Allow group 'Default'/'StorageAdmins' to manage volume-backups in tenancy
Allow group 'Default'/'StorageAdmins' to read volume-backups in tenancy
Allow group 'Default'/'StorageAdmins' to use volume-backups in tenancy where request.permission='VOLUME_BACKUP_COPY'
Allow group 'Default'/'StorageAdmins' to manage volume-group-backups in tenancy
Allow group 'Default'/'StorageAdmins' to manage boot-volume-backups in tenancy
Allow group 'Default'/'StorageAdmins' to use boot-volume-backups in tenancy where request.permission='BOOT_VOLUME_BACKUP_COPY'
```
#### Steps:
1. Navigate to:
   ```
   Storage > Block Volumes > Backups
   ```
2. **Verify**:
   - Ensure you can:
     - List all volume and boot volume backups (for `read volume-backups` and `inspect volume-backups`).
     - Copy backups (for `use volume-backups` and `use boot-volume-backups`).
     - Create, update, and delete backups (for `manage volume-backups` and `manage boot-volume-backups`).
   - Check if you can manage volume group backups under:
     ```
     Storage > Block Volumes > Volume Group Backups
     ```

---

### **4. Backup Policies**
#### Policies to Verify:
```plaintext
Allow group 'Default'/'StorageAdmins' to manage backup-policies in tenancy
Allow group 'Default'/'StorageAdmins' to manage backup-policy-assignments in tenancy
```
#### Steps:
1. Navigate to:
   ```
   Storage > Block Volumes > Backup Policies
   ```
2. **Verify**:
   - Ensure you can:
     - List all backup policies.
     - Create, update, and delete backup policies.
     - Assign policies to volumes (for `manage backup-policy-assignments`).

---

### **5. File Storage**
#### Policies to Verify:
```plaintext
Allow group 'Default'/'StorageAdmins' to manage file-family in tenancy
Allow group 'Default'/'StorageAdmins' to manage file-systems in tenancy
Allow group 'Default'/'StorageAdmins' to read mount-targets in tenancy
```
#### Steps:
1. Navigate to:
   ```
   Storage > File Storage
   ```
2. **Verify**:
   - Ensure you can:
     - List all file systems (for `inspect file-family`).
     - Create, update, and delete file systems (for `manage file-family` and `manage file-systems`).
     - View mount targets and their details (for `read mount-targets`).

---

### **6. Object Storage**
#### Policies to Verify:
```plaintext
Allow group 'Default'/'StorageAdmins' to manage buckets in tenancy
Allow group 'Default'/'StorageAdmins' to manage objects in tenancy
Allow group 'Default'/'StorageAdmins' to manage objects in tenancy where any {request.permission='OBJECT_CREATE', request.permission='OBJECT_INSPECT'}
Allow group 'Default'/'StorageAdmins' to read buckets in tenancy
Allow group 'Default'/'StorageAdmins' to read objects in tenancy
```
#### Steps:
1. Navigate to:
   ```
   Storage > Object Storage
   ```
2. **Verify**:
   - Buckets:
     - Ensure you can list all buckets (for `read buckets`).
     - Create, update, and delete buckets (for `manage buckets`).
   - Objects:
     - Ensure you can list objects in buckets (for `read objects`).
     - Upload, delete, and manage objects (for `manage objects`).

---

### **How to Confirm Each Policy**
After completing each step:
1. **Verify Action Permissions**:
   - If you can perform the required action without seeing "Authorization Failed" errors, the policy is working.
2. **Troubleshoot Issues**:
   - If actions fail, verify the user is part of the `StorageAdmins` group.
   - Ensure policies have propagated (wait 5-10 minutes and log out/log back in).
   - Double-check policy syntax.

---



### **Full Policy Set Summary**
Here’s the cleaned and validated list of policies for `StorageAdmins`:
```plaintext
Allow group 'Default'/'StorageAdmins' to manage volumes in tenancy
Allow group 'Default'/'StorageAdmins' to inspect volumes in tenancy
Allow group 'Default'/'StorageAdmins' to manage volume-groups in tenancy
Allow group 'Default'/'StorageAdmins' to inspect volume-groups in tenancy
Allow group 'Default'/'StorageAdmins' to manage volume-group-backups in tenancy
Allow group 'Default'/'StorageAdmins' to manage volume-backups in tenancy
Allow group 'Default'/'StorageAdmins' to read volume-backups in tenancy
Allow group 'Default'/'StorageAdmins' to use volume-backups in tenancy where request.permission='VOLUME_BACKUP_COPY'
Allow group 'Default'/'StorageAdmins' to manage boot-volume-backups in tenancy
Allow group 'Default'/'StorageAdmins' to use boot-volume-backups in tenancy where request.permission='BOOT_VOLUME_BACKUP_COPY'
Allow group 'Default'/'StorageAdmins' to manage backup-policies in tenancy
Allow group 'Default'/'StorageAdmins' to manage backup-policy-assignments in tenancy
Allow group 'Default'/'StorageAdmins' to manage file-family in tenancy
Allow group 'Default'/'StorageAdmins' to manage file-systems in tenancy
Allow group 'Default'/'StorageAdmins' to read mount-targets in tenancy
Allow group 'Default'/'StorageAdmins' to manage buckets in tenancy
Allow group 'Default'/'StorageAdmins' to manage objects in tenancy
Allow group 'Default'/'StorageAdmins' to manage objects in tenancy where any {request.permission='OBJECT_CREATE', request.permission='OBJECT_INSPECT'}
Allow group 'Default'/'StorageAdmins' to read buckets in tenancy
Allow group 'Default'/'StorageAdmins' to read objects in tenancy
```

Let me know if you need further clarification or assistance!



