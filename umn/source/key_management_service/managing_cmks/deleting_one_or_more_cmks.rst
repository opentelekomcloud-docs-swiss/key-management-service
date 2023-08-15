:original_name: kms_01_0072.html

.. _kms_01_0072:

Deleting One or More CMKs
=========================

Before deleting the CMK, confirm that it is not in use and will not be used.

-  Check the CMK permission to determine its possible usage scope. For details, see :ref:`Querying a Grant <kms_01_0030>`.
-  Check audit logs to determine the actual usage.

Prerequisites
-------------

-  The CMK you want to schedule deletion for is in **Enabled** or **Disabled** status.

Constraints
-----------

-  A key will not be deleted until its scheduled deletion period expires. You can set the period to a value within the range 7 to 1096 days.

   Before the specified deletion date, you can cancel the deletion if you want to use the CMK. Once the scheduled deletion has taken effect, the CMK will be deleted permanently and you will not be able to decrypt data encrypted by the CMK. Exercise caution when performing this operation.

-  Default Master Keys created by KMS cannot be scheduled for deletion.

-  A CMK in pending deletion status does not incur charges. If you cancel deletion, the charging resumes from the time when the CMK was scheduled to be deleted.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Click |image2|. Choose **Security** > **Key Management Service**. The **Key Management Service** page is displayed.
#. In the row containing the desired CMK, click **Delete**.
#. In the dialog box that is displayed, enter the number of days after which you want the deletion to take effect.

   .. note::

      -  A key will not be deleted until its scheduled deletion period expires. You can set the period to a value within the range 7 to 1096 days. Before the specified deletion date, you can cancel the deletion if you want to use the CMK.
      -  A CMK in pending deletion status does not incur charges. If you cancel deletion, the charging resumes from the time when the CMK was scheduled to be deleted.

#. In the dialog box that is displayed, select **I understand the impact of deleting keys** and click **Yes**.

   .. note::

      To schedule the deletion of multiple CMKs at a time, select them and click **Delete** in the upper left corner of the list.

.. |image1| image:: /_static/images/en-us_image_0000001284811084.png
.. |image2| image:: /_static/images/en-us_image_0000001295227514.png
