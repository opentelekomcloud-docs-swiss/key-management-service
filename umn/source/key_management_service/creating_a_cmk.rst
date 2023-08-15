:original_name: kms_01_0178.html

.. _kms_01_0178:

Creating a CMK
==============

This section describes how to create a CMK on the KMS console.

Constraints
-----------

-  You can create up to 100 CMKs, excluding default master keys.
-  Aliases of default master keys end with **/default**. Therefore, in choosing aliases for your CMKs, do not use aliases ending with **/default**.
-  KMS does not limit the number of times that a CMK can be called.

Scenarios
---------

-  Encrypt data in OBS
-  Encrypt data in EVS
-  Encrypt data in IMS
-  Encrypt an RDS DB instance
-  Direct encryption and decryption of small volumes of data
-  DEK encryption and decryption for user applications


Creating a CMK
--------------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2|. Choose **Security** > **Key Management Service**. The **Key Management Service** page is displayed.

#. Click **Create Key** in the upper right corner.

#. Configure parameters in the **Create Key** dialog box.

   -  **Alias** is the alias of the CMK to be created.

      .. note::

         -  You can enter digits, letters, underscores (_), hyphens (-), colons (:), and slashes (/).
         -  You can enter up to 255 characters.

   -  **Key Algorithm**: Select a key algorithm. For more information, see :ref:`Table 1 <kms_01_0178__en-us_topic_0112947540_table0624027274>`.

      .. _kms_01_0178__en-us_topic_0112947540_table0624027274:

      .. table:: **Table 1** Key algorithms supported by KMS

         +----------------+----------------+--------------------+------------------------------------+-----------------------------------------------------------------------------+
         | Key Type       | Algorithm Type | Key Specifications | Description                        | Usage                                                                       |
         +================+================+====================+====================================+=============================================================================+
         | Symmetric key  | AES            | AES_256            | AES symmetric key                  | Encrypts and decrypts a small amount of data or data keys.                  |
         +----------------+----------------+--------------------+------------------------------------+-----------------------------------------------------------------------------+
         | Asymmetric key | RSA            | -  RSA_2048        | RSA asymmetric password            | Encrypts and decrypts a small amount of data or creates digital signatures. |
         |                |                | -  RSA_3072        |                                    |                                                                             |
         |                |                | -  RSA_4096        |                                    |                                                                             |
         +----------------+----------------+--------------------+------------------------------------+-----------------------------------------------------------------------------+
         |                | ECC            | -  EC_P256         | Elliptic curve recommended by NIST | Digital signature                                                           |
         |                |                | -  EC_P384         |                                    |                                                                             |
         +----------------+----------------+--------------------+------------------------------------+-----------------------------------------------------------------------------+

   -  **Usage**: Select **SIGN_VERIFY** or **ENCRYPT_DECRYPT**.

      -  For a symmetric key, the default value is **ENCRYPT_DECRYPT**.
      -  For RSA asymmetric keys, select **ENCRYPT_DECRYPT** or **SIGN_VERIFY**. The default value is **SIGN_VERIFY**.
      -  For an ECC asymmetric key, the default value is **SIGN_VERIFY**.

      .. note::

         The key usage can only be configured during key creation and cannot be modified afterwards.

   -  (Optional) **Description** is the description of the CMK.

      .. note::

         You can enter up to 255 characters.

#. (Optional) Add tags to the CMK as needed, and enter the tag key and tag value.

   .. note::

      -  When a CMK has been created without any tag, you can add a tag to the CMK later as necessary. Click the alias of the CMK, click the **Tags** tab, and click **Add Tag**.
      -  The same tag (including tag key and tag value) can be used for different CMKs. However, under the same CMK, one tag key can have only one tag value.
      -  A maximum of 20 tags can be added for one CMK.
      -  If you want to delete a tag from the tag list when adding multiple tags, you can click **Delete** in the row where the tag to be added is located to delete the tag.

#. Click **OK**. A message is displayed in the upper right corner of the page, indicating that the key is created successfully.

   In the CMK list, you can view created CMKs. The default status of a CMK is **Enabled**.

Related Operations
------------------

-  For details about how to upload objects with server-side encryption, see section "Uploading a File with Server-Side Encryption" in the `Object Storage Service User Guide <https://docs.sc.otc.t-systems.com/usermanual/obs/en-us_topic_0045853692.html>`__.
-  For details about how to encrypt data on EVS disks, see section "Creating an EVS Disk" in the `Elastic Volume Service User Guide <https://docs.sc.otc.t-systems.com/en-us/usermanual/evs/evs_01_0119.html>`__.
-  For details about how to encrypt private images, see section "Encrypting an Image" in the `Image Management Service User Guide <https://docs.sc.otc.t-systems.com/en-us/ims/index.html>`__.
-  For details about how to create a DEK and a plaintext-free DEK, see sections "Creating a DEK" and "Creating a Plaintext-Free DEK" in the `Key Management Service API Reference <https://docs.sc.otc.t-systems.com/api/kms/kms_02_0050.html>`__.
-  For details about how to encrypt and decrypt a DEK for a user application, see sections "Encrypting a DEK" and "Decrypting a DEK" in the `Key Management Service API Reference <https://docs.sc.otc.t-systems.com/api/kms/kms_02_0050.html>`__.

.. |image1| image:: /_static/images/en-us_image_0000001284811084.png
.. |image2| image:: /_static/images/en-us_image_0000001295227514.png
