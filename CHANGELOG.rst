
.. Copyright Planetmint GmbH and Planetmint contributors
   SPDX-License-Identifier: (Apache-2.0 AND CC-BY-4.0)
   Code is Apache-2.0 and docs are CC-BY-4.0

Changelog
=========

0.14.0 (2022-12-02)
-------------------
Fixed
^^^^^
* reintegrated delegated signing support into the driver


0.13.0 (2022-11-28)
-------------------
Changed
^^^^^^^
* adjusted to changes in planetmint-transactions@0.2.2 that are a result from the zenroom upgrade and package renaming

0.12.0 (2022-10-27)
-------------------
Changed
^^^^^^^
* replaced common module with planetmint-transactions package
* adjusted for asset changes in planetmint-transactions@0.2.0

0.11.0 (2022-09-15)
-------------------
Changed
^^^^^^^
* Breaking: fixed the faulty default placemnt of the "data"-tag into assets. Thereby caused obfuscation got removed.
* Breaking: adjusted to the IPLD definitions of planetmint.

0.6.2 (2022-09-08)
------------------
Changed
^^^^^^^
* In setup.py, changed crypto-conditions dependency to above 0.10.0


0.6.2 (2018-11-03)
------------------
Changed
^^^^^^^
* In setup.py, changed python-rapidjson==0.6.0 to ~=0.6.0,
  and changed requests>=2.11.0 to >=2.20.0

0.6.1 (2018-10-21)
------------------
Fixed
^^^^^
* Fixed the problem with a docs page (Handcrafting Transactions) that wouldn't build.

0.6.0 (2018-10-20)
------------------
Changed
^^^^^^^
* Added support for deterministic keypair generation from a 32-byte seed.
  See pull request #487 by external contributor @excerebrose
* Pinned cryptoconditions==0.8.0 in setup.py

Removed
^^^^^^^
* The send() function was removed. See pull request #483.

Known issues
^^^^^^^^^^^^
* Builds of the Handcrafting Transactions page started failing again,
  in Travis CI and on ReadTheDocs.

0.5.3 (2018-09-12)
------------------
Changed
^^^^^^^
* Fixed a failing unit test
* Pinned cryptoconditions==0.7.2 in setup.py
* Fixed the Handcrafting Transactions page in the docs

0.5.2 (2018-08-31)
-------------------
Added
^^^^^

* Cap exponential backoff depending on timeout value for reasonable waiting time in event of network recovery. `#470 <https://github.com/planetmint/planetmint-driver/pull/470>`
* Update cryptoconditions dependency because of security vulnerability CVE-2018-10903. `#472 <https://github.com/planetmint/planetmint-driver/pull/472>`


0.5.1 (2018-08-23)
---------------------
Added
^^^^^

* Support for Planetmint server v2.0.0.b5.
* added round-robin strategy to connect to nodes of the Planetmint network `BEP 14 <https://github.com/planetmint/BEPs/tree/master/14>`_

0.5.0 (2018-06-14)
---------------------
Added
^^^^^
* Added three new methods to send/post a transaction as discussed `here <https://github.com/planetmint/planetmint/issues/2307>`_:

    * ``send_commit``
    * ``send_async``
    * ``send_sync``

Deprecated
^^^^^^^^^^
* ``send()`` under ``TransactionEndpoint``, and available
  via ``Planetmint.transactions``. Replaced by the above three methods:
  ``send_commit()``, ``send_async()``, and ``send_sync()``.


0.5.0a4 (2018-05-07)
---------------------
* `Removed dependencies from Planetmint Server package <https://github.com/planetmint/planetmint-driver/pull/411>`_.


0.5.0a2 (2018-04-18)
---------------------
* `The default mode for sending a transaction is now commit <https://github.com/planetmint/planetmint-driver/issues/386>`_.
* `The metadata endpoint was added <https://github.com/planetmint/planetmint-driver/issues/347>`_.
* Support for Planetmint server v2.0.0a2.


0.5.0a1 (2018-04-03)
--------------------
There were **many** changes between Planetmint 1.3 and Planetmint 2.0 Alpha, too many to list here. We wrote a series of blog posts to summarize most changes, especially those that affect end users and application developers:

* `Some HTTP API Changes in the Next Release <https://blog.planetmint.com/some-http-api-changes-in-the-next-release-49612a537b0c>`_.
* `Three Transaction Model Changes in the Next Release <https://blog.planetmint.com/three-transaction-model-changes-in-the-next-release-dadbac50094a>`_.


0.4.1 (2017-08-02)
------------------
Fixed
^^^^^
* Handcrafting transactions documentation. `Pull request #312
  <https://github.com/planetmint/planetmint-driver/pull/312>`_.
* Quickstart guide. `Pull request #316
  <https://github.com/planetmint/planetmint-driver/pull/316>`_.

0.4.0 (2017-07-05)
------------------
Added
^^^^^
* Support for Planetmint server (HTTP API) 1.0.0.

0.3.0 (2017-06-23)
------------------
Added
^^^^^
* Support for Planetmint server (HTTP API) 1.0.0rc1.
* Support for crypto-conditions RFC draft version 02.
* Added support for text search endpoint ``/assets?search=``

0.2.0 (2017-02-06)
------------------
Added
^^^^^
* Support for Planetmint server 0.9.
* Methods for ``GET /`` and ``GET /api/v1``

Changed
^^^^^^^
* Node URLs, passed to ``Planetmint()`` MUST not include the api prefix
  ``'/api/v1'``, e.g.:

    * BEFORE: ``http://localhost:9984/api/v1``
    * NOW: ``http://localhost:9984``

0.1.0 (2016-11-29)
------------------
Added
^^^^^
* Support for Planetmint server 0.8.0.
* Support for divisible assets.

Removed
^^^^^^^
* ``create()`` and ``transfer()`` under ``TransactionEndpoint``, and available
  via ``Planetmint.transactions``. Replaced by the three "canonical"
  transaction operations: ``prepare()``, ``fulfill()``, and ``send()``.
* Support for client side timestamps.


0.0.3 (2016-11-25)
------------------
Added
^^^^^
* Support for "canonical" transaction operations:

    * ``prepare``
    * ``fulfill``
    * ``send``

Deprecated
^^^^^^^^^^
* ``create()`` and ``transfer()`` under ``TransactionEndpoint``, and available
  via ``Planetmint.transactions``. Replaced by the above three "canonical"
  transaction operations: ``prepare()``, ``fulfill()``, and ``send()``.

Fixed
^^^^^
* ``Planetmint()`` default node setting on its transport class. See commit
  `0a80206 <https://github.com/planetmint/planetmint-driver/commit/0a80206407ef155d220d25a337dc9a4f51046e70>`_


0.0.2 (2016-10-28)
------------------

Added
^^^^^
* Support for Planetmint server 0.7.0


0.0.1dev1 (2016-08-25)
----------------------

* Development (pre-alpha) release on PyPI.

Added
^^^^^
* Minimal support for ``POST`` (via ``create()`` and ``transfer()``), and
  ``GET`` operations on the ``/transactions`` endpoint.


0.0.1a1 (2016-08-12)
--------------------

* Planning release on PyPI.
