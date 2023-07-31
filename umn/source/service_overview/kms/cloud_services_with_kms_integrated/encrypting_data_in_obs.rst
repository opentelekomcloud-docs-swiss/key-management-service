:original_name: kms_01_0007.html

.. _kms_01_0007:

Encrypting Data in OBS
======================

-  When using Object Storage Service (OBS) to upload files with server-side encryption, you can select KMS encryption and use the key provided by KMS to encrypt the files to be uploaded. For more information about OBS, see the `Object Storage Service User Guide <https://docs.sc.otc.t-systems.com/usermanual/obs/en-us_topic_0045853692.html>`__.

   There are two types of CMKs that can be used:

   -  The default master key **obs/default** created by KMS
   -  CMKs that you create on the KMS console using KMS-generated key materials

-  Alternatively, you can call OBS APIs to upload a file with server-side encryption using KMS-managed keys (SSE-KMS). For details, see the `Object Storage Service API Reference <https://docs.sc.otc.t-systems.com/api/obs/obs_04_0001.html>`__.
