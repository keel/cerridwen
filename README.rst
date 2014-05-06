Cerridwen
=========

Cerridwen provides data on the moon that is suitable
for both astronomical and astrological purposes. It
comes with a simple command-line utility and a JSON
server.

The motivation for this package is to have a reliable
open-source library and API that provides data on the
moon and, eventually, other planetary bodies at a certain
point in time.


.. contents::
   :depth: 1


Requirements
------------

Cerridwen depends on Python 3. You might be able to make
it work with Python 2 as well. Patches welcome! Please let
me know if there's a version of Python 3 that does not
run Cerridwen properly.

It also depends on these packages:

* pyswisseph, the Python interface to the Swiss Ephemeris library

* numpy, which Cerridwen uses for its ephemeris calculations

* Flask, if you wish to run Cerridwen's API server


Quickstart
----------

::

  $ pip install cerridwen

To test Cerridwen's data on the console, invoke:

::

  $ cerridwen

If everything is to your satisfaction you can then
start the API server:

::

  $ cerridwen-server

It will start up in the foreground and listen on port 2828,
serving moon data via HTTP in JSON format at the URI `/v1/moon`.

You can test it as follows:

::

  $ curl http://localhost:2828/v1/moon

This should give you a proper JSON response with
the current moon data.

Change the listen port by passing the -p switch to cerridwen-server,
followed by the desired port.


FAQ
---

What's the guaranteed precision of the generated data?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

For new and full moons (and other angles) the maximum error is smaller than 1/10^6.


What zodiac is used for the longitudes?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

All longitudes whether absolute or relative use the tropical zodiac, i.e. zero degrees
refers to zero degrees tropical Aries, which in turn corresponds to the sun's position
at the vernal equinox of the year in question.


What about other planetary bodies?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The source code is designed to be easily extensible to other planets and points.
The goal is to add more planets once the moon interface is reasonably mature.


Will you add more moon data?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Yes! For example equatorial latitude, lunation number and rise/set times.


How can I help?
^^^^^^^^^^^^^^^

First and foremost: use it! Also: tell your friends and fellow astronomers/astrologers!

You can also help write docs, contribute source code and tell me what you'd like
to see in the project.

Donations are also welcome.


Licensing
---------

Cerridwen is distributed under the MIT license, as follows.

Copyright (c) 2014 Leslie P. Polzer <leslie.polzer@gmx.net>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
