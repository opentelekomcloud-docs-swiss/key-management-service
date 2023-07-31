:original_name: kms_01_0029.html

.. _kms_01_0029:

Creating a Grant
================

You can create grants for other users or accounts to use the CMK. You can create a maximum of 100 grants on a CMK.

Prerequisites
-------------

-  You have obtained the ID of the grantee (user to whom permissions are to be authorized).
-  The desired CMK is in **Enabled** status.

Constraints
-----------

The owner of a CMK can create a grant for the CMK on the KMS console or by calling APIs. The users or accounts who have the grant creation permission assigned by the owner of the CMK can create grants for the CMK only by calling APIs.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2|. Choose **Security** > **Key Management Service**. The **Key Management Service** page is displayed.

#. Click the alias of the desired CMK to go to the page displaying its details to create a grant on it.

#. Click the **Grants** tab.

#. Click **Create Grant**. The **Create Grant** dialog box is displayed.

#. In the dialog box that is displayed, enter the ID of the user to be authorized and select permissions to be granted. For more information, see :ref:`Table 1 <kms_01_0029__en-us_topic_0112947581_t4212c2dc877a41ba8f1db3dfa2ed7575>`.

   .. important::

      A grantee can perform the authorized operations only by calling the necessary APIs. For details, see the *Key Management Service API Reference*.

   .. _kms_01_0029__en-us_topic_0112947581_t4212c2dc877a41ba8f1db3dfa2ed7575:

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
      | Parameter             | Description                                                                                                                                                                                                                             | Example Value                    |
      +=======================+=========================================================================================================================================================================================================================================+==================================+
      | Key ID                | ID of a CMK (automatically read by the system)                                                                                                                                                                                          | ``-``                            |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
      | User or Tenant        | Whether a user or an account is authorized.                                                                                                                                                                                             | d9a6b2bdaedd4ba586cabe6372d1b312 |
      |                       |                                                                                                                                                                                                                                         |                                  |
      |                       | -  User                                                                                                                                                                                                                                 |                                  |
      |                       |                                                                                                                                                                                                                                         |                                  |
      |                       |    User ID: Enter the IAM user ID. To obtain the ID, click the username in the upper right corner of the page, choose **My Credentials**. Choose **API Credentials** from the navigation pane, and copy the value of **IAM User ID**.   |                                  |
      |                       |                                                                                                                                                                                                                                         |                                  |
      |                       |    After the authorization is complete, the IAM user can use the specified keys.                                                                                                                                                        |                                  |
      |                       |                                                                                                                                                                                                                                         |                                  |
      |                       | -  Account                                                                                                                                                                                                                              |                                  |
      |                       |                                                                                                                                                                                                                                         |                                  |
      |                       |    Account ID: Enter the IAM user ID. To obtain the ID, click the username in the upper right corner of the page, choose **My Credentials**. Choose **API Credentials** from the navigation pane, and copy the value of **Account ID**. |                                  |
      |                       |                                                                                                                                                                                                                                         |                                  |
      |                       |    After the authorization is complete, all IAM users under the account can use specified keys.                                                                                                                                         |                                  |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
      | Operations            | The following permissions can be authorized:                                                                                                                                                                                            | ``-``                            |
      |                       |                                                                                                                                                                                                                                         |                                  |
      |                       | .. note::                                                                                                                                                                                                                               |                                  |
      |                       |                                                                                                                                                                                                                                         |                                  |
      |                       |    -  You can create multiple grants on a CMK to provide different permissions to the same user. The user's permissions on the CMK are the combination of all the grants.                                                               |                                  |
      |                       |    -  This parameter cannot be left blank.                                                                                                                                                                                              |                                  |
      |                       |    -  Selecting only **Create Grant** is not allowed.                                                                                                                                                                                   |                                  |
      |                       |                                                                                                                                                                                                                                         |                                  |
      |                       | -  **Create Data Key Without Plaintext**                                                                                                                                                                                                |                                  |
      |                       | -  **Create Data Key**                                                                                                                                                                                                                  |                                  |
      |                       | -  **Encrypt Data Key**                                                                                                                                                                                                                 |                                  |
      |                       | -  **Decrypt Data Key**                                                                                                                                                                                                                 |                                  |
      |                       | -  **Query Key Information**                                                                                                                                                                                                            |                                  |
      |                       | -  **Create Grant**                                                                                                                                                                                                                     |                                  |
      |                       | -  **Retire Grant**                                                                                                                                                                                                                     |                                  |
      |                       |                                                                                                                                                                                                                                         |                                  |
      |                       |    -  A grantee can retire a grant if the grantee does not need that permission.                                                                                                                                                        |                                  |
      |                       |    -  If, before retiring a grant, the grantee has granted the permission to another user, that user's permission will not be affected by the grant retirement.                                                                         |                                  |
      |                       |                                                                                                                                                                                                                                         |                                  |
      |                       | -  **Encrypt Data**                                                                                                                                                                                                                     |                                  |
      |                       | -  **Decrypt Data**                                                                                                                                                                                                                     |                                  |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+

#. Click **OK**. When message **Grant created successfully** is displayed in the upper right corner, the grant has been created.

   In the list of grants, you can view the grant ID, grant type, grantee ID, granted operation, and creation time of the grant.

.. |image1| image:: /_static/images/en-us_image_0000001284811084.png
.. |image2| image:: /_static/images/en-us_image_0000001295227514.png
