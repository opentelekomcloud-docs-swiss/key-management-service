:original_name: kms_01_0030.html

.. _kms_01_0030:

Querying a Grant
================

This section describes how to view the details about a grant on the KMS console, such as the grant ID, grantee user ID, granted operation, and creation time.

Prerequisites
-------------

You have created a grant.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2|. Choose **Security** > **Key Management Service**. The **Key Management Service** page is displayed.

#. Click the alias of the desired CMK to view its details.

#. Click the **Grants** tab. Information about the CMK and grants created on it are displayed.

   :ref:`Table 1 <kms_01_0030__en-us_topic_0112947514_t0484dc5b4d9e4d86a61df05bffcaecf3>` describes the parameters.

   .. _kms_01_0030__en-us_topic_0112947514_t0484dc5b4d9e4d86a61df05bffcaecf3:

   .. table:: **Table 1** Parameter description

      +--------------------+-----------------------------------------------------------------------------------+
      | Parameter          | Description                                                                       |
      +====================+===================================================================================+
      | Grant ID           | Randomly generated unique identification of a grant                               |
      +--------------------+-----------------------------------------------------------------------------------+
      | Granted To         | Whether permissions are granted to a user or account.                             |
      +--------------------+-----------------------------------------------------------------------------------+
      | Grantee ID         | ID of the authorized user or account.                                             |
      +--------------------+-----------------------------------------------------------------------------------+
      | Granted Operations | Authorized operations (such as **Create Data Key**) on the CMK                    |
      +--------------------+-----------------------------------------------------------------------------------+
      | Creation Time      | Creation time of the grant                                                        |
      +--------------------+-----------------------------------------------------------------------------------+
      | Operation          | Operations that can be performed on a grant. For example, you can revoke a grant. |
      +--------------------+-----------------------------------------------------------------------------------+

#. Click a grant ID to view the grant details.

.. |image1| image:: /_static/images/en-us_image_0000001284811084.png
.. |image2| image:: /_static/images/en-us_image_0000001295227514.png
