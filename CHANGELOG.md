Release notes
=============

This document describes all the changes made to the *Interinstitutional
Agreement CNR API* document, starting from its first beta draft version.


2.0.3
-----

* Update documentation after requiring client CNR implementation.


2.0.2
-----

* Added a better explanation of what "properly received" means.


2.0.1
-----

* Fix invalid `schemaLocation` (use absolute URL).


2.0.0
-----

 * This API now requires implementers to upgrade their implementations to
   [Version 2](https://github.com/erasmus-without-paper/ewp-specs-sec-intro/tree/stable-v2)
   of the *Authentication and Security* document.

   In particular, this means that the clients MUST be aware of the fact, that
   the server is no longer required to support methods of authentication and
   encryption which it *was* required to support in the previous versions of
   this API. Clients SHOULD consult the newly introduced `<http-security>`
   element in the server's manifest entry before making their requests.

 * Because we are releasing a new major release (which is no longer
   backward-compatible with the previously released stable `1.x.x` releases),
   XML namespaces were changed to reflect that.

   In particular, API-entry namespace was changed from:

   ```
   https://github.com/erasmus-without-paper/ewp-specs-api-iia-cnr/blob/stable-v1/manifest-entry.xsd
   ```

   to:

   ```
   https://github.com/erasmus-without-paper/ewp-specs-api-iia-cnr/blob/stable-v2/manifest-entry.xsd
   ```

   And the response namespace was changed from:

   ```
   https://github.com/erasmus-without-paper/ewp-specs-api-iia-cnr/tree/stable-v1
   ```

   to:

   ```
   https://github.com/erasmus-without-paper/ewp-specs-api-iia-cnr/tree/stable-v2
   ```


1.0.1
-----

* Explicitly declare that this version still requires the use of
  [Version 1](https://github.com/erasmus-without-paper/ewp-specs-sec-intro/tree/stable-v1)
  of the *Authentication and Security* document. You can find more information
  on the planned process of updating security requirements
  [here](https://github.com/erasmus-without-paper/ewp-specs-sec-intro/issues/1).


1.0.0
-----

* First stable release.


0.2.0
-----

* Changed XML namespaces (as part of
  [this issue](https://github.com/erasmus-without-paper/ewp-specs-api-iias/issues/22)).
  Since this version, this API is in the `stable-v1` XML namespace.

* Fixed a couple of invalid links in the documents.


0.1.2
-----

* `minOccurs` and `maxOccurs` are now provided explicitly
  ([why?](https://github.com/erasmus-without-paper/general-issues/issues/22)).

* Updated links.


0.1.1
-----

* Just added a link to a CNR introduction chapter.


0.1.0
-----

Initial release.
