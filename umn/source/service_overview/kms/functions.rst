:original_name: kms_01_0005.html

.. _kms_01_0005:

Functions
=========

KMS is a secure, reliable, and easy-to-use cloud service that helps users create, manage, and protect keys in a centralized manner.

It uses Hardware Security Modules (HSMs) to protect keys. All CMKs are protected by root keys in HSMs to avoid key leakage.

It also controls access to keys and records all operations on keys with traceable logs. In addition, it provides use records of all keys, meeting your audit and regulatory compliance requirements.


Functions
---------

-  On the KMS console, you can perform the following operations on CMKs:

   -  Creating, querying, enabling, disabling, scheduling the deletion of, and canceling the deletion of CMKs
   -  Modifying the alias and description of CMKs
   -  Using the Online Tool to Encrypt and Decrypt Small-Size Data
   -  Importing CMKs and deleting CMK material
   -  Adding, searching for, editing, and deleting tags
   -  Creating, canceling, and querying grants

-  You can use the API to perform the following operations:

   -  Creating, encrypting, or decrypting data encryption keys (DEKs)
   -  Retiring grants

   For details, see the `Key Management Service API Reference <https://docs.sc.otc.t-systems.com/api/kms/kms_02_0050.html>`__.

-  Generate hardware true random number.

   You can generate 512-bit random numbers using the KMS API. The 512-bit hardware true random numbers can be used as or serve as basis for key materials and encryption parameters. For details, see the `Key Management Service API Reference <https://docs.sc.otc.t-systems.com/api/kms/kms_02_0050.html>`__.

Cryptographic Algorithms Supported by KMS
-----------------------------------------

:ref:`Table 1 <kms_01_0005__en-us_topic_0112947601_tc7ccf66255f74e4a8a34c7dbf91b9e91>` describes the key wrapping encryption and decryption algorithms supported by imported keys.

.. _kms_01_0005__en-us_topic_0112947601_tc7ccf66255f74e4a8a34c7dbf91b9e91:

.. table:: **Table 1** Key wrapping algorithms

   +-----------------------+---------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------+
   | Algorithm             | Description                                                                                                         | Configuration                                                                                                          |
   +=======================+=====================================================================================================================+========================================================================================================================+
   | RSAES_OAEP_SHA_256    | RSA encryption algorithm that uses OAEP and has the **SHA-256** hash function                                       | Select an encryption algorithm based on your HSM functions.                                                            |
   |                       |                                                                                                                     |                                                                                                                        |
   |                       |                                                                                                                     | #. If your HSM supports the **RSAES_OAEP_SHA_256** algorithm, use **RSAES_OAEP_SHA_256** to encrypt key materials.     |
   |                       |                                                                                                                     | #. If your HSM does not support **OAEP**, use **RSAES_PKCS1_V1_5** to encrypt key materials.                           |
   |                       |                                                                                                                     |                                                                                                                        |
   |                       |                                                                                                                     | .. important::                                                                                                         |
   |                       |                                                                                                                     |                                                                                                                        |
   |                       |                                                                                                                     |    NOTICE:                                                                                                             |
   |                       |                                                                                                                     |    The **RSAES_OAEP_SHA_1** encryption algorithm is no longer secure. Exercise caution when performing this operation. |
   +-----------------------+---------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------+
   | RSAES_PKCS1_V1_5      | Rivest-Shamir_Adleman (RSA) encryption algorithm (v1.5) of Public-Key Cryptography Standards number 1 (PKCS #1)     |                                                                                                                        |
   +-----------------------+---------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------+
   | RSAES_OAEP_SHA_1      | RSA encryption algorithm that uses Optimal Asymmetric Encryption Padding (OAEP) and has the **SHA-1** hash function |                                                                                                                        |
   +-----------------------+---------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------+
