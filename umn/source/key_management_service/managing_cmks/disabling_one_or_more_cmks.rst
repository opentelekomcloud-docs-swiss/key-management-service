:original_name: kms_01_0035.html

.. _kms_01_0035:

Disabling One or More CMKs
==========================

This section describes how to use the KMS console to disable one or more CMKs, thereby protecting data in urgent cases.

After being disabled, a CMK cannot be used to encrypt or decrypt any data. Before using a disabled CMK to encrypt or decrypt data, you must enable it by following instructions in :ref:`Enabling One or More CMKs <kms_01_0034>`.

Prerequisites
-------------

The CMK you want to disable is in **Enabled** status.

Constraints
-----------

-  Default master keys created by KMS cannot be disabled.
-  A disabled CMK is still billable. It will stop incurring charges if it is deleted.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Click |image2|. Choose **Security** > **Key Management Service**. The **Key Management Service** page is displayed.
#. In the row containing the desired CMK, click **Disable**.
#. In the dialog box that is displayed, select **I understand the impact of disabling keys** and click **Yes**.

   .. note::

      To disable multiple CMKs at a time, select them and click **Disable** in the upper left corner of the list.

.. |image1| image:: /_static/images/en-us_image_0000001284811084.png
.. |image2| image:: /_static/images/en-us_image_0000001295227514.png
