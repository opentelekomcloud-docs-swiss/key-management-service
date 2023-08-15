:original_name: kms_01_0009.html

.. _kms_01_0009:

Encrypting Data in IMS
======================

-  When uploading an image file to Image Management Service (IMS), you can choose to encrypt the image file using a key provided by KMS to protect the file. For details, see the `Image Management Service User Guide <https://docs.sc.otc.t-systems.com/usermanual/ims/en-us_topic_0013901623.html>`__.

   There are two types of CMKs that can be used:

   -  The default master key **ims/default** created by KMS
   -  CMKs that you create on the KMS console using KMS-generated key materials

-  You can also call IMS APIs to create encrypted image files. For details, see `Image Management Service API Reference <https://docs.sc.otc.t-systems.com/api/ims/en-us_topic_0121588329.html>`__.
