:original_name: kms_01_0104.html

.. _kms_01_0104:

What Is a Default Master Key?
=============================

A Default Master Key is automatically created by another cloud service using KMS, such as Object Storage Service (OBS). The alias of a Default Master Key ends with **/default**.

You can use the management console to query but cannot disable or schedule the deletion of Default Master Keys.

.. table:: **Table 1** Default Master Keys

   =========== ==============================
   Alias       Cloud Service
   =========== ==============================
   obs/default Object Storage Service (OBS)
   evs/default Elastic Volume Service (EVS)
   ims/default Image Management Service (IMS)
   =========== ==============================

.. note::

   A Default Master Key is automatically created when a user employs the KMS encryption function for the first time in another cloud service.
