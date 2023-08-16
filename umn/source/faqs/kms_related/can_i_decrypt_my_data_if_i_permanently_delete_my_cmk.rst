:original_name: kms_01_0059.html

.. _kms_01_0059:

Can I Decrypt My Data if I Permanently Delete My CMK?
=====================================================

No.

If you have permanently deleted your CMK, the data encrypted using it cannot be decrypted. If the scheduled deletion date of the CMK has not arrived, you can cancel the scheduled deletion.

If the CMK is created using imported key material and only the key material is deleted, you can import the local backup of the key material to the CMK and reclaim the user data. If the key material is not backed up locally, user data cannot be reclaimed.
