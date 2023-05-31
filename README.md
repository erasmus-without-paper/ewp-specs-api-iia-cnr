Interinstitutional Agreement CNR API
====================================

* [What is the status of this document?][statuses]
* [See the index of all other EWP Specifications][develhub]


Summary
-------

This document describes the **Interinstitutional Agreement CNR API**.
This API can be implemented by all EWP partners, and will be called by some
other EWP partners whenever related IIAs are changed on their side. It allows
the partners to listen for changes in other copies of their IIAs kept in the
EWP Network.

CNR stands for Change Notification Receiver. For a detailed introduction on how
CNR APIs work, please read [this page][cnr-intro].


Request method
--------------

 * Requests MUST be made with HTTP POST method. Servers MAY reject all other
   request methods.


Request parameters
------------------

Parameters MUST be provided in the regular `application/x-www-form-urlencoded`
format.



### `iia_id` (required)

Identifier of the IIA which has recently been changed (created, updated or
deleted) by the calling HEI.


Security
--------

This version of this API uses [standard EWP Authentication and Security,
Version 2][sec-v2]. Server implementers choose which security methods they
support by declaring them in their Manifest API entry.

This API does not expose any sensitive data, it only notifies the server that
it should reload portions of its data. For this reason, it is RECOMMENDED for
server implementers to not be overly strict on security methods they require
(i.e. it is RECOMMENDED to *not* require extra layers of encryption in requests
and responses - TLS seems more than enough).


Handling of invalid parameters
------------------------------

 * General [error handling rules][error-handling] apply.

 * Servers MUST return a valid (HTTP 200) XML response whenever the request has
   been [properly received][bad-cnr-request]. Unless HTTP 200 is received,
   clients are RECOMMENDED to automatically retry the request after some time.


Response
--------

Servers MUST respond with a valid XML document described by the
[response.xsd](response.xsd) schema. See the schema annotations for further
information.


Keep in mind that...
--------------------

It is NOT guaranteed that all notifications will be delivered to you promptly.
Some notifications may also **not reach you at all**, e.g. due to
implementation errors on the sending institution's server.


[develhub]: http://developers.erasmuswithoutpaper.eu/
[statuses]: https://github.com/erasmus-without-paper/ewp-specs-management#statuses
[registry-spec]: https://github.com/erasmus-without-paper/ewp-specs-api-registry
[discovery-api]: https://github.com/erasmus-without-paper/ewp-specs-api-discovery
[echo]: https://github.com/erasmus-without-paper/ewp-specs-api-echo
[error-handling]: https://github.com/erasmus-without-paper/ewp-specs-architecture#error-handling
[institutions-api]: https://github.com/erasmus-without-paper/ewp-specs-api-institutions
[iias-api]: https://github.com/erasmus-without-paper/ewp-specs-api-iias
[iia-search-api]: https://github.com/erasmus-without-paper/ewp-specs-api-iia-search
[cnr-intro]: https://github.com/erasmus-without-paper/ewp-specs-architecture#cnr
[bad-cnr-request]: https://github.com/erasmus-without-paper/ewp-specs-architecture#bad-cnr-request
[sec-v2]: https://github.com/erasmus-without-paper/ewp-specs-sec-intro/tree/stable-v2
