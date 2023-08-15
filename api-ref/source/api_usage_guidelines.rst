:original_name: kms_02_0050.html

.. _kms_02_0050:

API Usage Guidelines
====================

Cloud service APIs comply with the RESTful API design principles. REST-based Web services are organized into resources. Each resource is identified by one or more Uniform Resource Identifiers (URIs). An application accesses a resource based on the resource's Unified Resource Locator (URL). A URL is usually in the following format: *https://Endpoint/uri*. In the URL, **uri** indicates the resource path, that is, the API access path.

Cloud service APIs use HTTPS as the transmission protocol. Requests/Responses are transmitted by using JSON messages, with media type represented by **Application/json**.
