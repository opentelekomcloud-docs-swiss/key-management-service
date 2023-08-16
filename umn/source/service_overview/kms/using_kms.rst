:original_name: kms_01_0015.html

.. _kms_01_0015:

Using KMS
=========

Interacting with Cloud Services
-------------------------------

Cloud services use the envelope encryption technology and call KMS APIs to encrypt service resources. Your CMKs are under your own management. With your grant, cloud services use a specific CMK of yours to encrypt data.

The encryption process is as follows:

#. Create a CMK on KMS.
#. Cloud services call the **create-datakey** API of the KMS to create a DEK. Then you get a plaintext DEK and a ciphertext DEK.

   .. note::

      Ciphertext DEKs are generated when you use a CMK to encrypt the plaintext DEKs.

#. Cloud services use the plaintext DEK to encrypt a plaintext file, generating a ciphertext file.
#. Cloud services store the ciphertext DEK and ciphertext file in a persistent storage device or a storage service.

.. note::

   When users download the data from a cloud service, the service uses the CMK specified by KMS to decrypt the ciphertext DEK, uses the decrypted DEK to decrypt data, and then provides the decrypted data for users to download.

.. table:: **Table 1** List of cloud services that use KMS encryption

   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Service Name                      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
   +===================================+==============================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================+
   | Object Storage Service (OBS)      | You can upload objects to and download them from Object Storage Service (OBS) in common mode or server-side encryption mode. When you upload objects in encryption mode, data is encrypted at the server side and then securely stored on OBS in ciphertext. When you download encrypted objects, the data in ciphertext is decrypted at the server side and then provided to you in plaintext. OBS supports the server-side encryption with KMS-managed keys (SSE-KMS) mode. In SSE-KMS mode, OBS uses the keys provided by KMS for server-side encryption. |
   |                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
   |                                   | For details about how to upload objects to OBS in SSE-KMS mode, see the `Object Storage Service User Guide <https://docs.sc.otc.t-systems.com/usermanual/obs/en-us_topic_0045853692.html>`__.                                                                                                                                                                                                                                                                                                                                                                |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Elastic Volume Service (EVS)      | If you enable the encryption function when creating an EVS disk, the disk will be encrypted with the DEK generated by using your CMK. Data stored in the EVS disk will be automatically encrypted.                                                                                                                                                                                                                                                                                                                                                           |
   |                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
   |                                   | For details about how to use the encryption function of EVS, see `Elastic Volume Service User Guide <https://docs.sc.otc.t-systems.com/en-us/usermanual/evs/evs_01_0119.html>`__.                                                                                                                                                                                                                                                                                                                                                                            |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Image Management Service (IMS)    | When creating a private image using an external image file, you can enable the private image encryption function and select a CMK provided by KMS to encrypt the image.                                                                                                                                                                                                                                                                                                                                                                                      |
   |                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
   |                                   | For details about how to use the private image encryption function of Image Management Service (IMS), see `Image Management Service User Guide <https://docs.sc.otc.t-systems.com/usermanual/ims/en-us_topic_0013901623.html>`__.                                                                                                                                                                                                                                                                                                                            |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Working with User Applications
------------------------------

To encrypt plaintext data, a user application can call the necessary KMS API to create a DEK. The DEK can then be used to encrypt the plaintext data. Then the application can store the encrypted data. In addition, the user application can call the KMS API to create CMKs. DEKs can be stored in ciphertext after being encrypted with the CMKs.

Envelope encryption is implemented, with CMKs stored in KMS and ciphertext DEKs in user applications. KMS is called to decrypt a ciphertext DEK only when necessary.

The encryption process is as follows:

#. .. _kms_01_0015__en-us_topic_0171265817_li12558154594712:

   The application calls the **create-key** API of KMS to create a CMK.

#. The application calls the **create-datakey** API of KMS to create a DEK. A plaintext DEK and a ciphertext DEK are generated.

   .. note::

      Ciphertext DEKs are generated when you use a CMK to encrypt the plaintext DEKs in :ref:`1 <kms_01_0015__en-us_topic_0171265817_li12558154594712>`.

#. The application uses the plaintext DEK to encrypt a plaintext file. A ciphertext file is generated.

#. The application saves the ciphertext DEK and the ciphertext file together in a persistent storage device or a storage service.

For details, see the `Key Management Service API Reference <https://docs.sc.otc.t-systems.com/api/kms/kms_02_0050.html>`__.
