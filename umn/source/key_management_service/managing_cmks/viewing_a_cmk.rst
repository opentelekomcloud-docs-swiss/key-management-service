:original_name: kms_01_0096.html

.. _kms_01_0096:

Viewing a CMK
=============

This section describes how to view the information about the master key on the KMS console, including the key alias, status, ID, and creation time. The status of a CMK can be **Enabled**, **Disabled**, **Pending deletion**, or **Pending import**.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Click |image2|. Choose **Security** > **Key Management Service**. The **Key Management Service** page is displayed.

4. Check the key list.

   .. table:: **Table 1** Key list parameters

      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                              |
      +===================================+==========================================================================================================+
      | Alias                             | Alias of a CMK                                                                                           |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Status                            | Status of a CMK, which can be one of the following:                                                      |
      |                                   |                                                                                                          |
      |                                   | -  **Enabled**                                                                                           |
      |                                   |                                                                                                          |
      |                                   |    The CMK is enabled.                                                                                   |
      |                                   |                                                                                                          |
      |                                   | -  **Disabled**                                                                                          |
      |                                   |                                                                                                          |
      |                                   |    The CMK is disabled.                                                                                  |
      |                                   |                                                                                                          |
      |                                   | -  **Pending deletion**                                                                                  |
      |                                   |                                                                                                          |
      |                                   |    The CMK is scheduled for deletion.                                                                    |
      |                                   |                                                                                                          |
      |                                   | -  **Pending import**                                                                                    |
      |                                   |                                                                                                          |
      |                                   |    If your CMK does not have materials, its status is **Pending import**.                                |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | ID                                | Random ID of a CMK generated during the CMK creation                                                     |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Creation Time                     | Creation time of the CMK                                                                                 |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Key Algorithm and Usage           | Key algorithm selected during key creation and its usage                                                 |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Origin                            | Source of key material, which can be one of the following:                                               |
      |                                   |                                                                                                          |
      |                                   | -  **External**                                                                                          |
      |                                   |                                                                                                          |
      |                                   |    The key is imported to the KMS from an external system.                                               |
      |                                   |                                                                                                          |
      |                                   | -  **Key Management Service**                                                                            |
      |                                   |                                                                                                          |
      |                                   |    The key is a default master key or created in KMS.                                                    |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Operation                         | Operations you can perform on the CMK, such as disable, delete, import key material, or cancel deletion. |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+

5. You can click the alias of a CMK to view its details.

   .. note::

      To change the alias or description of the CMK, click |image3| next to the value of **Alias** or **Description**.

      -  A default master key (the alias suffix of which is **/default**) does not allow alias and description changes.
      -  The alias and description of a CMK cannot be changed if the CMK is in **Pending deletion** status.

.. |image1| image:: /_static/images/en-us_image_0000001284811084.png
.. |image2| image:: /_static/images/en-us_image_0000001295227514.png
.. |image3| image:: /_static/images/en-us_image_0231665754.png
