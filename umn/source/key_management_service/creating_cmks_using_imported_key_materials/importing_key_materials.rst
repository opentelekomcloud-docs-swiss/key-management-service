:original_name: kms_01_0055.html

.. _kms_01_0055:

Importing Key Materials
=======================

If you want to use your own key materials instead of the KMS-generated materials, you can use the console to import your key materials to KMS. CMKs created using imported materials and KMS-generated materials are managed together by KMS.

This section describes how to import key materials on the KMS console.

.. note::

   -  A CMK with imported material works in the same way as one using KMS-generated material, that is, you enable and disable them as well as schedule their deletion and cancel their scheduled deletion in the same way.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2|. Choose **Security** > **Key Management Service**. The **Key Management Service** page is displayed.

#. Click **Import Key**. The **Import Key** dialog box is displayed.

#. Configure key parameters.

   -  **Alias** is the alias of the CMK to be created.

      .. note::

         -  You can enter digits, letters, underscores (_), hyphens (-), colons (:), and slashes (/).
         -  You can enter up to 255 characters.

   -  **Key Algorithm**: Select a key algorithm. For more information, see :ref:`Table 1 <kms_01_0055__en-us_topic_0112947677_en-us_topic_0112947540_table0624027274>`.

      .. _kms_01_0055__en-us_topic_0112947677_en-us_topic_0112947540_table0624027274:

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

      -  If a CMK was created without any tag, you can add a tag to the CMK later as necessary. Click the alias of the CMK, click the **Tags** tab, and click **Add Tag**.
      -  The same tag (including tag key and tag value) can be used for different CMKs. However, under the same CMK, one tag key can have only one tag value.
      -  A maximum of 20 tags can be added for each CMK.
      -  If you want to delete a tag from the tag list when adding multiple tags, you can click **Delete** in the row where the tag to be added is located to delete the tag.

#. Click **security and durability** to understand the security and durability of the imported key.

#. Select **I understand the security and durability of using an imported key**, and create a CMK whose key material is empty.

#. Click **Next** to go to the **Download the Import Items** step. Select a key wrapping algorithm based on :ref:`Table 2 <kms_01_0055__en-us_topic_0112947677_table4398144917230>`.

   .. _kms_01_0055__en-us_topic_0112947677_table4398144917230:

   .. table:: **Table 2** Key wrapping algorithms

      +-----------------------+---------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------+
      | Algorithm             | Description                                                                                                         | Configuration                                                                                                          |
      +=======================+=====================================================================================================================+========================================================================================================================+
      | RSAES_OAEP_SHA_256    | RSA encryption algorithm that uses OAEP and has the **SHA-256** hash function                                       | Select an encryption algorithm based on your HSM functions.                                                            |
      |                       |                                                                                                                     |                                                                                                                        |
      |                       |                                                                                                                     | a. If the HSMs support the **RSAES_OAEP_SHA_256** algorithm, use **RSAES_OAEP_SHA_256** to encrypt key materials.      |
      |                       |                                                                                                                     | b. If the HSMs do not support **OAEP**, use **RSAES_PKCS1_V1_5** to encrypt key materials.                             |
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

   .. note::

      If you stop a key material import process and want to try again, click **Import Key Material** in the row of the required CMK, and import key material in the dialog box that is displayed.

#. Obtain the wrapping key and import token.

   a. .. _kms_01_0055__en-us_topic_0112947677_li2844626114317:

      Obtain the wrapping key and import token.

      -  Method 1: Click **Download**. The downloaded files include the wrapping key, import token, and description file, as shown below.


         .. figure:: /_static/images/en-us_image_0000001490096349.png
            :alt: **Figure 1** Downloading a file

            **Figure 1** Downloading a file

         -  **wrappingKey\_**\ *KeyID*\ \_\ *DownloadTime* is the wrapping key. It is encoded in binary format and used to encrypt the wrapping key of the key material.
         -  **importToken**\ \_\ *KeyID*\ \_\ *DownloadTime* is a token used to import key materials to KMS.
         -  **README\_**\ *KeyID*\ \_\ *DownloadTime* is a description file recording information such as a CMK's serial number, wrapping algorithm, wrapping key name, token file name, and the expiration time of the token file and wrapping key.

         .. important::

            The wrapping key and import token expire in 24 hours. If they have expired, download them again.

      -  Method 2: Obtain the wrapping key and import token by calling APIs.

         #. Call the **get-parameters-for-import** API to obtain the wrapping key and import token.

            -  **public_key**: content of the wrapping key (Base-64 encoding) returned after the API call
            -  **import_token**: content of the import token (Base-64 encoding) returned after the API call

            The following example describes how to obtain the wrapping key and import token of a CMK (ID: **43f1ffd7-18fb-4568-9575-602e009b7ee8**; encryption algorithm: **RSAES_OAEP_SHA_256**).

            -  Example request

               .. code-block::

                  {
                      "key_id": "43f1ffd7-18fb-4568-9575-602e009b7ee8",
                      "wrapping_algorithm":"RSAES_OAEP_SHA_256"
                  }

            -  Example response

               .. code-block::

                  {
                      "key_id": "43f1ffd7-18fb-4568-9575-602e009b7ee8",
                      "public_key":"public key base64 encoded data",
                      "import_token":"import token base64 encoded data",
                      "expiration_time":1501578672
                  }

         #. Save the wrapping key and convert its format. Only the key material encrypted using the converted wrapping key can be imported to the management console.

            #. Copy the content of the wrapping key **public_key**, paste it to a .txt file, and save the file as **PublicKey.b64**.

            #. Use OpenSSL to run the following command to perform Base-64 coding on the content of the **PublicKey.b64** file to generate binary data, and save the converted file as **PublicKey.bin**:

               **openssl** **enc** **-d** **-base64** **-A** **-in** **PublicKey.b64** **-out** **PublicKey.bin**

         #. Save the import token, copy the content of the **import_token** token, paste it to a .txt file, and save the file as **ImportToken.b64**.

   b. Use the wrapping key to encrypt the key material.

      .. note::

         After performing this step, you will obtain either of the following files:

         Symmetric key scenario: **EncryptedKeyMaterial.bin** (key material)

         Asymmetric key scenario: **EncryptedKeyMaterial.bin** (temporary key material) and **out_rsa_private_key.der** (private key ciphertext)

      Method 1: Use the downloaded wrapping key to encrypt key materials on your HSM.

      Method 2: Use OpenSSL to generate a key material and use the downloaded wrapping key to encrypt the key material.

      .. note::

         If you need to run the **openssl pkeyutl** command, ensure your OpenSSL version is 1.0.2 or later.

      #. Generate a key material (256-bit symmetric key) and save it as **PlaintextKeyMaterial.bin**.

         -  If the AES256 symmetric key algorithm is used, run the following command on the client where the OpenSSL tool has been installed:

            **openssl** **rand** **-out** **PlaintextKeyMaterial.bin** **32**

         -  If the SA and ECC asymmetric key algorithms are used, run the following command on the client where the OpenSSL tool has been installed:

            #. Generate a hexadecimal AES256 key.

               **openssl rand -out 0xPlaintextKeyMaterial.bin -hex 32**

            #. Convert the hexadecimal AES256 key to the binary format.

               **cat 0xPlaintextKeyMaterial.bin \| xxd -r -ps > PlaintextKeyMaterial.bin**

      #. .. _kms_01_0055__en-us_topic_0112947677_li12585410398:

         Use the downloaded wrapping key to encrypt the key material and save the encrypted key material as **EncryptedKeyMaterial.bin**.

         If the wrapping key was downloaded from the console, replace **PublicKey.bin** in the following command with the wrapping key name *wrappingKey_keyID_DownloadTime*.

         .. table:: **Table 3** Encrypting the generated key material using the downloaded wrapping key

            +-----------------------------------+------------------------------------------------------------------------+
            | Wrapping Key Algorithm            | Key Material Encryption                                                |
            +===================================+========================================================================+
            | RSAES_OAEP_SHA_256                | **openssl** **pkeyutl**                                                |
            |                                   |                                                                        |
            |                                   | **-in** **PlaintextKeyMaterial.bin**                                   |
            |                                   |                                                                        |
            |                                   | **-inkey** **PublicKey.bin**                                           |
            |                                   |                                                                        |
            |                                   | **-out** **EncryptedKeyMaterial.bin**                                  |
            |                                   |                                                                        |
            |                                   | **-keyform** **der**                                                   |
            |                                   |                                                                        |
            |                                   | **-pubin** **-encrypt**                                                |
            |                                   |                                                                        |
            |                                   | **-pkeyopt** **rsa_padding_mode:oaep** **-pkeyopt rsa_oaep_md:sha256** |
            +-----------------------------------+------------------------------------------------------------------------+

      #. .. _kms_01_0055__en-us_topic_0112947677_li287144863910:

         (Optional) To import an asymmetric key, generate an asymmetric private key, use the temporary key material (**EncryptedKeyMaterial.bin**) to encrypt the private key, and import the encrypted file as the private key ciphertext.

         -  Take the RSA4096 algorithm as an example. Perform the following operations:

            #. Generate a private key.

               **openssl genrsa -out rsa_private_key.pem 4096**

            #. Convert the key to DER format.

               **openssl pkcs8 -topk8 -inform PEM -outform DER -in rsa_private_key.pem -out rsa_private_key.der -nocrypt**

            #. Use a temporary key material to encrypt the private key.

               **openssl enc -id-aes256-wrap-pad -K $(cat 0xPlaintextKeyMaterial.bin) -iv A65959A6 -in rsa_private_key.der -out out_rsa_private_key.der**

               .. note::

                  By default, the -id-aes256-wrap-pad algorithm is not enabled in OpenSSL. To wrap a key, upgrade OpenSSL to the latest version and patch it first. For details, see :ref:`Why Can't I Wrap Asymmetric Keys by Using -id-aes256-wrap-pad in OpenSSL? <kms_01_0186>`.

#. Click **Next**.The **Import Key Material** page is displayed.

   .. table:: **Table 4** Parameters for importing key materials (for symmetric keys)

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                   |
      +===================================+===============================================================================================================================+
      | Key ID                            | Random ID of a CMK generated during the CMK creation                                                                          |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------+
      | Key material                      | Import a key material.                                                                                                        |
      |                                   |                                                                                                                               |
      |                                   | For example, use the **EncryptedKeyMaterial.bin** file in :ref:`10.b.ii <kms_01_0055__en-us_topic_0112947677_li12585410398>`. |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------+

   .. table:: **Table 5** Parameters for importing key materials (for asymmetric keys)

      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                       |
      +===================================+===================================================================================================================================+
      | Key ID                            | Random ID of a CMK generated during the CMK creation                                                                              |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+
      | Temporary key material            | Import a temporary key material.                                                                                                  |
      |                                   |                                                                                                                                   |
      |                                   | For example, select the **EncryptedKeyMaterial.bin** file in :ref:`10.b.ii <kms_01_0055__en-us_topic_0112947677_li12585410398>`.  |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+
      | Private key ciphertext            | Select private key ciphertext.                                                                                                    |
      |                                   |                                                                                                                                   |
      |                                   | For example, select the **out_rsa_private_key.der** file in :ref:`10.b.iii <kms_01_0055__en-us_topic_0112947677_li287144863910>`. |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+

#. Click **Next** to go to the **Import Key Token** step. Configure the parameters as described in :ref:`Table 6 <kms_01_0055__en-us_topic_0112947677_tf00e7c9f3be04375a6ceb8b65a9b1697>`.

   .. _kms_01_0055__en-us_topic_0112947677_tf00e7c9f3be04375a6ceb8b65a9b1697:

   .. table:: **Table 6** Parameters for importing a key token

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                  |
      +===================================+==============================================================================================================================================================================================================+
      | Key ID                            | Random ID of a CMK generated during the CMK creation                                                                                                                                                         |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Key import token                  | Select the token downloaded in :ref:`10.a <kms_01_0055__en-us_topic_0112947677_li2844626114317>`.                                                                                                            |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Key material expiration mode      | -  **Key material will never expire**: You use this option to specify that key materials will not expire after import.                                                                                       |
      |                                   |                                                                                                                                                                                                              |
      |                                   | -  **Key material will expire**: You use this option to specify the expiration time of the key materials. By default, key materials expire in 24 hours after import.                                         |
      |                                   |                                                                                                                                                                                                              |
      |                                   |    After the key material expires, the system automatically deletes the key material within 24 hours. Once the key material is deleted, the key cannot be used and its status changes to **Pending import**. |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**. When the **Key imported successfully** message is displayed in the upper right corner, the materials are imported.

   .. important::

      Key materials can be successfully imported when they match the corresponding CMK ID and token.

   Your imported materials are displayed in the list of CMKs. The default status of an imported CMK is **Enabled**.

.. |image1| image:: /_static/images/en-us_image_0000001284811084.png
.. |image2| image:: /_static/images/en-us_image_0000001295227514.png
