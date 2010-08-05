.. Sinon.JS documentation master file, created by
   sphinx-quickstart on Wed Aug  4 22:58:44 2010.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Sinon.JS documentation
======================

Standalone test spies, stubs and mocks for JavaScript. No dependencies, works
with any unit testing framework.

Goals of Sinon
--------------

Sinon.JS was originally developed for the book `Test-Driven JavaScript
Development`__. Although there are already quite a few similar libraries out
there, I had some specific design requirements which were not `all` satisfied
by the ones I tried:

.. __: http://www.amazon.com/dp/0321683919/


 * **Standalone**. There's no reason to tie stubbing and mocking to a specific
   testing library. Granted, some aspects can be automated when doing so, but
   such integration can be provided for standalone libraries as well.
 * **Minimal global footprint**. The test environment is the last environment
   you want massive global pollution. The stub and mock API should live within
   a single object.
 * **Easy to use**. That's probably a given, but some of the mocking solutions
   I've seen requires unnecessary amounts of scaffolding to get going.
 * **Easy to integrate**. Making up for being standalone, I want the (minimal)
   scaffolding to be easy to automate with any testing library.
 * **CommonJS compliant**. Work both in browsers and on the server using
   CommonJS modules.

Sinon.JS satisfies these requirements. It's standalone, it lives entirely within
the ``sinon`` object, has a (hopefully) simple API and provides lots of tools to
reduce the required amount of scaffolding.

Documentation is organized by concepts. For example, under "Test spies" you will
find an explanation of test spies and how Sinon.JS implements them as well as
related API documentation.

.. toctree::
   :maxdepth: 2

   tutorial
   spies
   stubs
   mocks
   test_cases
   collections
   fake_time
   fake_xhr
   sandboxes
