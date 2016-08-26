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


Request method
--------------

 * Requests MUST be made with HTTP POST method. Servers MAY reject all other
   request methods.


Request parameters
------------------

Parameters MUST be provided in the regular `application/x-www-form-urlencoded`
format.


### `notifier_hei_id` (required)

Identifier of the HEI which has recently updated their copy of the IIA on their
servers, and is now sending the notification about this event.

Server implementers SHOULD verify if the request is signed with a proper client
certificate bound to this HEI.


### `iia_id` (required)

Identifier of the IIA which has recently been changed (created, updated or
deleted) on the notifier-HEI's servers.


Permissions
-----------

* Servers MUST allow this API to be called at least by all EWP Hosts which
  cover any HEI.


Handling of invalid parameters
------------------------------

 * General [error handling rules][error-handling] apply.

 * Please note, that receiving unknown `iia_id` values is NOT an error, and you
   MUST return a proper HTTP 200 response in this case. This usually indicates
   that a new IIA related with your institution has been created on some other
   institution's servers, and you may want to fetch it.


Response
--------

Servers MUST respond with a valid XML document described by the [response.xsd]
(response.xsd) schema. See the schema annotations for further information.


Keep in mind that...
--------------------

It is NOT guaranteed that all notifications will be delivered to you promptly.
Some notifications may also **not reach you at all**, because not every server
sends such notifications.


[develhub]: http://developers.erasmuswithoutpaper.eu/
[statuses]: https://github.com/erasmus-without-paper/ewp-specs-management#statuses
[registry-spec]: https://github.com/erasmus-without-paper/ewp-specs-api-registry
[discovery-api]: https://github.com/erasmus-without-paper/ewp-specs-api-discovery
[echo]: https://github.com/erasmus-without-paper/ewp-specs-api-echo
[error-handling]: https://github.com/erasmus-without-paper/ewp-specs-architecture#error-handling
[institutions-api]: https://github.com/erasmus-without-paper/ewp-specs-api-institutions
[iias-api]: https://github.com/erasmus-without-paper/ewp-specs-api-iias
[iia-search-api]: https://github.com/erasmus-without-paper/ewp-specs-api-iia-search
