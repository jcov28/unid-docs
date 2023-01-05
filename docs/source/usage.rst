Usage
=====

Using ``unid`` should not be a difficult
feat. We have created a few examples below
to get you started. You can always view the
more advanced documentation for more
information on upcoming and current features.

.. _installation:

Installation
------------

unid requires an installation via pip

.. code-block:: console

   (.venv) $ pip install unid==0.0.0rc10

Using ID Managers
----------------

To start using an ID Manager, you can use
the ``unid.IDManager`` class. Although there are
different classes, this one has the most
simplistic functionality for a first example.

The optional, ``overlay`` paramater allows you to
add overlays or overlay pipeline to change the
counter. A few examples of this functionality will
be showcased later.

The ``IDManager.new`` will generate and return a
new ID.

Below is a short example to use an ID Manager,

>>> import unid
>>> manager = unid.IDManager()
>>> id1 = manager.new
>>> id2 = manager.new
>>> manager.new
>>> id3 = manager.new
>>> print(id1, id2, id3)

Using Overlays
--------------

Overlays is one of the best key features included
in unid that sets it apart from our libraries and
utilties. There are a few different overlays that
you can pick from at the point of writing:

- ``unid.BinaryOverlay`` (or ``unid.Base2Overlay``)
- ``unid.OctalOverlay`` (or ``unid.Base8Overlay``)
- ``unid.Base10Overlay``
- ``unid.HexadecimalOverlay`` (or ``unid.Base16Overlay``)

For this example, we are going to use a binary
overlay (``unid.BinaryOverlay``). Note that each overlay
may also have an alias (such as shown above). You can
reference the overlays by either of the names. Below are a
few examples for using an overlay.

>>> # longer example
>>> import unid
>>> overlay = unid.BinaryOverlay()
>>> manager = unid.IDManager(overlay=overlay)
>>> print(manager.new)

And here's a shorter example,

>>> # shorter example
>>> import unid
>>> manager = unid.IDManager(overlay=unid.BinaryOverlay())
>>> print(manager.new)
