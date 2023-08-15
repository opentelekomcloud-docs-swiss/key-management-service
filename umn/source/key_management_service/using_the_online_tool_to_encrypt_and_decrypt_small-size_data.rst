:original_name: kms_01_0022.html

.. _kms_01_0022:

Using the Online Tool to Encrypt and Decrypt Small-Size Data
============================================================

This section describes how to use the online tool to encrypt or decrypt small-size data (4 KB or smaller) on the KMS console.

Prerequisites
-------------

The desired CMK is in **Enabled** status.

Encrypting Data
---------------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Click |image2|. Choose **Security** > **Key Management Service**. The **Key Management Service** page is displayed.

4. Click the alias of the desired CMK to view its details, and go to the online tool for data encryption and decryption.
5. Click **Encrypt**. In the text box on the left, enter the data to be encrypted.
6. Click **Execute**. Ciphertext of the data is displayed in the text box on the right.

   .. note::

      -  Use the current CMK to encrypt the data.
      -  You can click **Clear** to clear the entered data.
      -  You can click **Copy to Clipboard** to copy the ciphertext and save it in a local file.

Decrypting Data
---------------

#. Log in to the management console.
#. Click |image3|. Choose **Security** > **Key Management Service**. The **Key Management Service** page is displayed.

3. You can click any CMK in **Enabled** status to go to the encryption and decryption page of the online tool.
4. Click **Decrypt**. In the text box on the left, enter the data to be decrypted.

   .. note::

      -  The tool will identify the original encryption CMK and use it to decrypt the data.
      -  However, if the CMK has been deleted, the decryption fails.

5. Click **Execute**. Plaintext of the data is displayed in the text box on the right.

   .. note::

      You can click **Copy to Clipboard** to copy the plaintext and save it in a local file.

.. |image1| image:: /_static/images/en-us_image_0000001284811084.png
.. |image2| image:: /_static/images/en-us_image_0000001295227514.png
.. |image3| image:: /_static/images/en-us_image_0000001295227514.png
