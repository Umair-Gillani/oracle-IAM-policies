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

### **How to Verify These Policies**

1. **Volumes and Backups**:
   - Navigate to:
     ```
     Storage > Block Volumes
     ```
   - Confirm you can:
     - Create, update, and delete volumes and backups.
     - View volume and backup details.

2. **File Storage**:
   - Navigate to:
     ```
     Storage > File Storage
     ```
   - Confirm you can:
     - Manage file systems and mount targets.

3. **Object Storage**:
   - Navigate to:
     ```
     Storage > Object Storage
     ```
   - Confirm you can:
     - Create, update, and delete buckets and objects.
     - View and download object details.

4. **Instances and Attachments**:
   - Navigate to:
     ```
     Compute > Instances
     ```
   - Confirm you can:
     - Inspect instances.
     - Inspect volume attachments.

5. **Backup Policies**:
   - Navigate to:
     ```
     Storage > Block Volumes > Backup Policies
     ```
   - Confirm you can:
     - Create and assign backup policies.

6. **Audit Logs** (if needed for compliance):
   - Navigate to:
     ```
     Identity & Security > Audit
     ```
   - Confirm you can view storage-related audit events.

---

### **SAMA Compliance Justification**
These policies ensure:
- **Operational control**: Full management of storage resources while restricting access to unnecessary areas.
- **Data protection**: Permissions for managing backups and encryption policies.
- **Governance**: Visibility into storage activities via audit logs and read-only permissions where appropriate.

Let me know if you encounter issues or need further assistance!


### ----





