:original_name: kms_01_0139.html

.. _kms_01_0139:

Enabling Key Rotation
=====================

This section describes how to enable rotation for a CMK on the KMS console.

By default, automatic key rotation is disabled for a CMK. Every time you enable key rotation, KMS automatically rotates CMKs based on the rotation period you set.

Prerequisites
-------------

-  The CMK is enabled.
-  The **Origin** of the CMK is **KMS**.

Constraints
-----------

A disabled CMK is never rotated, even if rotation is enabled for it.

KMS resumes rotation when this CMK is enabled. If you enable this CMK after one rotation period has passed, KMS will rotate it within 24 hours.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Click |image2|. Choose **Security** > **Key Management Service**. The **Key Management Service** page is displayed.

4. Click the alias of the desired CMK to view its details.
5. Click the **Rotation Policy** tab. The rotation switch is displayed.
6. Click |image3| to enable key rotation.
7. In the **Enable Rotation Policy** dialog box, set the rotation period and click **OK**.

   -  Set the rotation period (unit: day) to an integer in the range 30 to 365. The default value is **365**.
   -  After the setting takes effect, the new rotation period starts.
   -  Configure the period based on how often a CMK is used. If it is frequently used, configure a short period; otherwise, set a long one.

      .. note::

         -  A disabled CMK is never rotated, even if rotation is enabled for it.
         -  KMS resumes rotation when this CMK is enabled. If you enable this CMK after one rotation period has passed, KMS will rotate it within 24 hours.
         -  You can click |image4| to change the rotation period. After the period is changed, KMS rotates the CMK by the new period.

.. |image1| image:: /_static/images/en-us_image_0000001284811084.png
.. |image2| image:: /_static/images/en-us_image_0000001295227514.png
.. |image3| image:: /_static/images/en-us_image_0000001348333869.png
.. |image4| image:: /_static/images/en-us_image_0000001295496116.png
