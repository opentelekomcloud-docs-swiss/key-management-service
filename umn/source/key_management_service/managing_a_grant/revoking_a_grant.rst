:original_name: dew_01_0098.html

.. _dew_01_0098:

Revoking a Grant
================

You can revoke a grant on the KMS console in either of the following scenarios:

-  A grantee does not need the grant. (The grantee can either tell the user who has created the grant to revoke the grant or call the necessary API to revoke the grant directly.)
-  You do not want the grantee to have the grant.

When a grant is revoked, the grantee does not have the corresponding permission anymore. However, if the grantee has created the same grant to another user, permission of that user will not be affected.

This section describes how to revoke a grant on the KMS console.

Prerequisites
-------------

You have created a grant.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Click |image2|. Choose **Security** > **Key Management Service**. The **Key Management Service** page is displayed.
#. Click the alias of the desired CMK to view its details.
#. In the row of a grantee, click **Revoke Grant**.
#. In the dialog box that is displayed, click **Yes**. When **Grant revoked successfully** is displayed in the upper right corner, the grant has been revoked.

.. |image1| image:: /_static/images/en-us_image_0000001284811084.png
.. |image2| image:: /_static/images/en-us_image_0000001295227514.png
