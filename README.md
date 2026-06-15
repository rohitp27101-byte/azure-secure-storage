# 🔐 Azure Secure File Storage System

A hands-on cloud security project built on Microsoft Azure, demonstrating secure file storage using Blob Storage, Access Keys, SAS Tokens, and RBAC.

---

## 📌 Project Overview

This project focuses on building a **production-style secure storage system** on Azure — covering access control, temporary access tokens, and role-based permissions.

---

## 🏗️ Architecture

```
User
 ↓
Azure AD Login
 ↓
RBAC Authorization
 ↓
Azure Blob Storage
 ↓
Temporary SAS Token Access
```

---

## 🛠️ Services Used

| Service | Purpose |
|--------|---------|
| Azure Blob Storage | File storage (images, PDFs, docs) |
| Access Keys | Master-level storage authentication |
| SAS Tokens | Time-limited, scoped access URLs |
| RBAC (IAM) | Role-based access control for users |
| Azure AD | Identity and login management |

---

## 📋 Step-by-Step Implementation

### Phase 1 — Storage Account Setup
- Created a Storage Account (`securestorage123`) in **Central India** region
- Selected **Standard performance** and **LRS redundancy**
- Enabled **Secure Transfer Required**
- Disabled **Public Blob Access**

### Phase 2 — Blob Container
- Created a private container: `projectfiles`
- Set Public Access Level to **Private**
- Uploaded test files (image, PDF, TXT)

### Phase 3 — Access Keys
- Located **key1** and **key2** under Security + Networking
- Understood these are master credentials — never to be shared publicly

### Phase 4 — SAS Token
- Generated SAS Token with:
  - ✅ Read + Write permissions
  - ✅ HTTPS only
  - ✅ 1-hour expiry
- Tested the SAS URL in browser — file accessible ✅

### Phase 5 — RBAC Configuration
- Opened **Access Control (IAM)** on Storage Account
- Assigned role: `Storage Blob Data Reader`
- Verified access worked with role
- Removed role → access denied ✅

### Phase 6 — Security Hardening
- Disabled public blob access
- Enabled **Soft Delete** for accidental deletion recovery
- Enabled **Blob Versioning**

---

## 🧪 Testing Results

| Test | Expected | Result |
|------|----------|--------|
| Access without SAS | ❌ Denied | ✅ Passed |
| Access with SAS URL | ✅ Allowed | ✅ Passed |
| Access after RBAC removed | ❌ Denied | ✅ Passed |

---

## 🔒 Security Best Practices Followed

- ❌ Access Keys never shared or hardcoded
- ✅ SAS Tokens used for temporary access
- ✅ Minimum required permissions assigned via RBAC
- ✅ Public access completely disabled
- ✅ Soft delete enabled for data recovery

---

## 📚 What I Learned

- How Azure Blob Storage works
- Difference between Access Keys, SAS Tokens, and RBAC
- How to implement least-privilege access in cloud
- Importance of disabling public access on storage
- Real-world cloud security hardening techniques

---

## 🔗 References

- [Azure Blob Storage Docs](https://learn.microsoft.com/en-us/azure/storage/blobs/)
- [Azure RBAC Overview](https://learn.microsoft.com/en-us/azure/role-based-access-control/overview)
- [SAS Tokens Guide](https://learn.microsoft.com/en-us/azure/storage/common/storage-sas-overview)

---
