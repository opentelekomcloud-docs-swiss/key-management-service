:original_name: kms_01_0016.html

.. _kms_01_0016:

Related Services
================

OBS
---

Object Storage Service (OBS) is a cloud storage service optimized for storing massive amounts of data. It provides unlimited, secure, and highly reliable storage capabilities at a relatively low cost. KMS provides central management and control capabilities of CMKs for OBS. It is used for server-side encryption with KMS-managed keys (SSE-KMS) on OBS.

EVS
---

Elastic Volume Service (EVS) offers scalable block storage for cloud servers. With high reliability, high performance, and rich specifications, EVS disks can be used for distributed file systems, development and test environments, data warehouse applications, and high-performance computing (HPC) scenarios to meet diverse service requirements. KMS provides central management and control capabilities of CMKs for EVS. It is used for encryption in EVS.

IMS
---

Image Management Service (IMS) supports lifecycle management for images. KMS provides central management and control capabilities of CMKs for Image Management Service (IMS). It is used for private image encryption in IMS.

ECS
---

Elastic Cloud Server (ECS) is a basic computing component that consists of CPUs, memory, OS, and EVS. After creating an ECS, you can use it like your local computer or physical server.

Dedicated HSM can encrypt sensitive data in the service systems on your ECS. You can control the generation, storage, and access authorization of keys to ensure the integrity and confidentiality of data during transmission and storage.

CTS
---

Cloud Trace Service (CTS) provides you with a history of KMS operations. After the CTS service is enabled, you can view all generated traces to review and audit performed KMS operations. For details, see the `Cloud Trace Service User Guide <https://docs.sc.otc.t-systems.com/usermanual/cts/en-us_topic_0030598498.html>`__.

.. table:: **Table 1** KMS operations supported by CTS

   +-------------------------------------------+---------------+-------------------------------+
   | Operation                                 | Resource Type | Trace Name                    |
   +===========================================+===============+===============================+
   | Creating a CMK                            | cmk           | createKey                     |
   +-------------------------------------------+---------------+-------------------------------+
   | Creating a DEK                            | cmk           | createDataKey                 |
   +-------------------------------------------+---------------+-------------------------------+
   | Creating a plaintext-free DEK             | cmk           | createDataKeyWithoutPlaintext |
   +-------------------------------------------+---------------+-------------------------------+
   | Enabling a CMK                            | cmk           | enableKey                     |
   +-------------------------------------------+---------------+-------------------------------+
   | Disabling a CMK                           | cmk           | disableKey                    |
   +-------------------------------------------+---------------+-------------------------------+
   | Encrypting a DEK                          | cmk           | encryptDatakey                |
   +-------------------------------------------+---------------+-------------------------------+
   | Decrypting a DEK                          | cmk           | decryptDatakey                |
   +-------------------------------------------+---------------+-------------------------------+
   | Scheduling the deletion of a CMK          | cmk           | scheduleKeyDeletion           |
   +-------------------------------------------+---------------+-------------------------------+
   | Canceling the scheduled deletion of a CMK | cmk           | cancelKeyDeletion             |
   +-------------------------------------------+---------------+-------------------------------+
   | Generating random numbers                 | rng           | genRandom                     |
   +-------------------------------------------+---------------+-------------------------------+
   | Changing the alias of a CMK               | cmk           | updateKeyAlias                |
   +-------------------------------------------+---------------+-------------------------------+
   | Changing the description of a CMK         | cmk           | updateKeyDescription          |
   +-------------------------------------------+---------------+-------------------------------+
   | Prompting risks about CMK deletion        | cmk           | deleteKeyRiskTips             |
   +-------------------------------------------+---------------+-------------------------------+
   | Importing key material                    | cmk           | importKeyMaterial             |
   +-------------------------------------------+---------------+-------------------------------+
   | Deleting key material                     | cmk           | deleteImportedKeyMaterial     |
   +-------------------------------------------+---------------+-------------------------------+
   | Creating a grant                          | cmk           | createGrant                   |
   +-------------------------------------------+---------------+-------------------------------+
   | Retiring a grant                          | cmk           | retireGrant                   |
   +-------------------------------------------+---------------+-------------------------------+
   | Revoking a grant                          | cmk           | revokeGrant                   |
   +-------------------------------------------+---------------+-------------------------------+
   | Encrypting data                           | cmk           | encryptData                   |
   +-------------------------------------------+---------------+-------------------------------+
   | Decrypting data                           | cmk           | decryptData                   |
   +-------------------------------------------+---------------+-------------------------------+
   | Adding a tag                              | cmk           | createKeyTag                  |
   +-------------------------------------------+---------------+-------------------------------+
   | Deleting a tag                            | cmk           | deleteKeyTag                  |
   +-------------------------------------------+---------------+-------------------------------+
   | Adding or deleting tags in batches        | cmk           | batchCreateKeyTags            |
   +-------------------------------------------+---------------+-------------------------------+
   | Batch deleting tags                       | cmk           | batchDeleteKeyTags            |
   +-------------------------------------------+---------------+-------------------------------+
   | Enabling key rotation                     | cmk           | enableKeyRotation             |
   +-------------------------------------------+---------------+-------------------------------+
   | Modifying key rotation interval           | cmk           | updateKeyRotationInterval     |
   +-------------------------------------------+---------------+-------------------------------+
   | Disabling key rotation                    | cmk           | disableKeyRotation            |
   +-------------------------------------------+---------------+-------------------------------+

IAM
---

Identity and Access Management (IAM) provides the permission management function for KMS.

Only users who have KMS Administrator permissions can use KMS.

To apply for permissions, contact a user with Security Administrator permissions. For details, see the `Identity and Access Management User Guide <https://docs.sc.otc.t-systems.com/usermanual/iam/iam_01_0026.html>`__.
