:original_name: kms_01_0024.html

.. _kms_01_0024:

Adding a Tag
============

Tags are used to identify CMKs. You can add tags to CMKs so that you can classify CMKs, trace them, and collect their usage status according to the tags.

Constraints
-----------

Tags cannot be added to default master keys.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2|. Choose **Security** > **Key Management Service**. The **Key Management Service** page is displayed.

#. Click the alias of the desired CMK to view its details.

#. Click **Tags** to go to the tag management page.

#. Click **Add Tag**. In the **Add Tag** dialog box, enter the tag key and tag value. :ref:`Table 1 <kms_01_0024__en-us_topic_0112947600_t2276fe27aa3d4e03a154c9332ff563f6>` describes the parameters.

   .. note::

      If you want to delete a tag to be added when adding multiple tags, you can click **Delete** in the row where the tag to be added is located to delete the tag.

   .. _kms_01_0024__en-us_topic_0112947600_t2276fe27aa3d4e03a154c9332ff563f6:

   .. table:: **Table 1** Tag parameters

      +-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------+-----------------+
      | Parameter       | Description                                                                                                                                          | Value                                                               | Example Value   |
      +=================+======================================================================================================================================================+=====================================================================+=================+
      | Tag key         | Name of a tag.                                                                                                                                       | -  Mandatory.                                                       | cost            |
      |                 |                                                                                                                                                      | -  Each tag key must be unique under the same CMK.                  |                 |
      |                 | The same tag (including tag key and tag value) can be used for different CMKs. However, under the same CMK, one tag key can have only one tag value. | -  36 characters limit.                                             |                 |
      |                 |                                                                                                                                                      | -  The following character types are allowed:                       |                 |
      |                 | A maximum of 20 tags can be added for one CMK.                                                                                                       |                                                                     |                 |
      |                 |                                                                                                                                                      |    -  Uppercase letters                                             |                 |
      |                 |                                                                                                                                                      |    -  Lowercase letters                                             |                 |
      |                 |                                                                                                                                                      |    -  Digits                                                        |                 |
      |                 |                                                                                                                                                      |    -  Special characters, including hyphens (-) and underscores (_) |                 |
      +-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------+-----------------+
      | Tag value       | Value of the tag                                                                                                                                     | -  This parameter can be empty.                                     | 100             |
      |                 |                                                                                                                                                      | -  43 characters limit.                                             |                 |
      |                 |                                                                                                                                                      | -  The following character types are allowed:                       |                 |
      |                 |                                                                                                                                                      |                                                                     |                 |
      |                 |                                                                                                                                                      |    -  Uppercase letters                                             |                 |
      |                 |                                                                                                                                                      |    -  Lowercase letters                                             |                 |
      |                 |                                                                                                                                                      |    -  Digits                                                        |                 |
      |                 |                                                                                                                                                      |    -  Special characters, including hyphens (-) and underscores (_) |                 |
      +-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------+-----------------+

#. Click **OK** to complete.

.. |image1| image:: /_static/images/en-us_image_0000001284811084.png
.. |image2| image:: /_static/images/en-us_image_0000001295227514.png
