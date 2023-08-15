:original_name: kms_01_0008.html

.. _kms_01_0008:

Encrypting Data in EVS
======================

-  When purchasing a disk, you can choose **Advanced Settings** > **Configure** > **Encryption** to encrypt the disk using the key provided by KMS. For more information about EVS, see the `Elastic Volume Service User Guide <https://docs.sc.otc.t-systems.com/en-us/usermanual/evs/evs_01_0119.html>`__.

   .. note::

      Before you use the encryption function, EVS must be granted the permission to access KMS. If you have the right to grant the permission, you can grant the permission directly. If you do not have the permission, contact a user with the security administrator permissions to add the security administrator permission for you. Then, you can grant the permission. For more information about EVS, see the `Elastic Volume Service User Guide <https://docs.sc.otc.t-systems.com/en-us/usermanual/evs/evs_01_0119.html>`__.

   There are two types of CMKs that can be used:

   -  The default master key **evs/default** created by KMS
   -  CMKs that you create on the KMS console using KMS-generated key materials

-  You can also call EVS APIs to create encrypted EVS disks. For details, see the `Elastic Volume Service API Reference <https://docs.sc.otc.t-systems.com/api/evs/evs_04_0001.html>`__.
