Interinstitutional Mobility Agreement CNR API
=============================================

* [What is the status of this document?][statuses]
* [See the index of all other EWP Specifications][develhub]


Summary
-------

This document describes the **Interinstitutional Mobility Agreement CNR API**.
This API is implemented by the all EWP partners, and called by **EWP IMA
Repository** whenever related IMAs are changed. It allows the partners to
listen for changes in all of their IMAs.


Request method
--------------

 * Requests MUST be made with HTTP POST method. Servers MAY reject all other
   request methods.


Request parameters
------------------

Parameters MUST be provided in the `application/x-www-form-urlencoded` format.


### `ima_id` (repeatable, required)

A list of IMA identifiers - IDs of agreements that were recently updated (in
the *EWP IMA Repository*).

This parameter is *repeatable*, so the request MAY contain multiple occurrences
of it. The server SHOULD process all of them.


Permissions
-----------

* Servers MUST allow this API to be called *at least* by **EWP IMA
  Repository** (you can determine it by looking at the `<apis-implemented>` of
  the caller, as you did in [Echo API][echo]).
  
* Implementers MAY allow this API to be called by other clients too (but it is
  not required).


Handling of invalid parameters
------------------------------

 * General [error handling rules][error-handling] apply. 

 * Invalid (unknown) `ima_id` values MUST be ignored. Servers MUST return
   a valid (HTTP 200) XML response whenever the request has been properly
   received (even if it contained unknown values).


Response
--------

Servers MUST respond with a valid XML document described by the [response.xsd]
(response.xsd) schema. See the schema annotations for further information.


[develhub]: http://developers.erasmuswithoutpaper.eu/
[statuses]: https://github.com/erasmus-without-paper/ewp-specs-management#statuses
[registry-spec]: https://github.com/erasmus-without-paper/ewp-specs-api-registry
[discovery-api]: https://github.com/erasmus-without-paper/ewp-specs-api-discovery
[echo]: https://github.com/erasmus-without-paper/ewp-specs-api-echo
[error-handling]: https://github.com/erasmus-without-paper/ewp-specs-architecture#error-handling
[institutions-api]: https://github.com/erasmus-without-paper/ewp-specs-api-institutions
[imas-api]: https://github.com/erasmus-without-paper/ewp-specs-api-imas
