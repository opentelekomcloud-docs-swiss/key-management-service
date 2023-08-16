:original_name: kms_01_0017.html

.. _kms_01_0017:

Permissions Management
======================

If you want to assign different access permissions to employees in an enterprise for the KMS resources purchased on the cloud platform, you can use Identity and Access Management (IAM) to perform refined permission management. IAM provides identity authentication, permissions management, and access control, helping you secure the access to your cloud resources.

With IAM, you can use your account to create IAM users for your employees, and assign permissions to control their access to specific resource types. For example, if you have software developers and you want to assign them the permission to access KMS but not to delete KMS or its resources, then you can create an IAM policy to assign the developers the permission to access KMS but prevent them from deleting KMS related data.

If the system account has met your requirements and you do not need to create an independent IAM user for permission control, then you can skip this section. This will not affect other functions of KMS.

KMS Permissions
---------------

By default, new IAM users do not have permissions assigned. You need to add a user to one or more groups, and attach permissions policies or roles to these groups. Users inherit permissions from the groups they are added to and can perform specified operations on cloud services based on the permissions.

KMS is a project-level service deployed and accessed in specific physical regions. To assign permissions to a user group, specify the scope as region-specific projects and select projects for the permissions to take effect. If **All projects** is selected, the permissions will take effect for the user group in all region-specific projects. Users need to switch to the authorized region when accessing KMS.

You can grant users permissions by using roles and policies.

-  Roles: A type of coarse-grained authorization mechanism that defines permissions related to user responsibilities. This mechanism provides only a limited number of service-level roles for authorization. When using roles to grant permissions, you must also assign other roles that the permissions depend on to take effect. However, roles are not an ideal choice for fine-grained authorization and secure access control.
-  Policies: A type of fine-grained authorization mechanism that defines permissions required to perform operations on specific cloud resources under certain conditions. This mechanism allows for more flexible policy-based authorization, meeting requirements for secure access control. For example, you can grant KMS users only the permissions for managing a certain type of cloud servers. Most policies contain permissions for specific APIs, and permissions are defined using API actions.

For more information, see :ref:`Table 1 <kms_01_0017__en-us_topic_0169425412_table123532558115>`.

.. _kms_01_0017__en-us_topic_0169425412_table123532558115:

.. table:: **Table 1** KMS permissions

   +-------------------+--------------------------------------------------+-------------+------------+
   | Role/Policy Name  | Description                                      | Type        | Dependency |
   +===================+==================================================+=============+============+
   | KMS Administrator | Administrator permissions for the encryption key | System role | None       |
   +-------------------+--------------------------------------------------+-------------+------------+

The following table describes the common operations supported by each system-defined permission of KMS. Select the permissions as needed.

.. table:: **Table 2** Common operations supported by each system-defined policy or role

   ===================================== =================
   Operation                             KMS Administrator
   ===================================== =================
   Create a key                          Y
   Enable a key                          Y
   Disable a key                         Y
   Schedule key deletion                 Y
   Cancel scheduled key deletion         Y
   Modify a key alias                    Y
   Modify key description                Y
   Generate a random number              Y
   Create a DEK                          Y
   Create a plaintext-free DEK           Y
   Encrypt a DEK                         Y
   Decrypt a DEK                         Y
   Obtain parameters for importing a key Y
   Import key materials                  Y
   Delete key materials                  Y
   Create a grant                        Y
   Revoking a grant                      Y
   Retire a grant                        Y
   Query the grant list                  Y
   Query retirable grants                Y
   Encrypt data                          Y
   Decrypt data                          Y
   Enable key rotation                   Y
   Modify key rotation interval          Y
   Disable key rotation                  Y
   Query key rotation status             Y
   Query CMK instances                   Y
   Query key tags                        Y
   Query project tags                    Y
   Batch add or delete key tags          Y
   Add tags to a key                     Y
   Delete key tags                       Y
   Query the key list                    Y
   Query key details                     Y
   Query instance quantity               Y
   Query quotas                          Y
   ===================================== =================

Helpful Links
-------------

-  Two types of permission policies are provided by default: default policies and custom policies. Default policies are pre-defined by IAM and cannot be modified. If default policies do not meet your requirements, you can create custom policies for fine-grained permission control.
-  Configure permission policies for a user group and add users to the group so that these users can obtain operation permissions defined in the policies.
