Troubleshooting
===============

Debugging the issue
-------------------

Contact your service provider and provide them with any errors or logs that help describe the error
and issues you may be experiencing.

Service discovery
-----------------

Some clients - especially iOS - have problems finding the proper sync URL, even when explicitly
configured to use it.

There are several techniques to remedy this, which are described extensively at the
`Sabre DAV website <http://sabre.io/dav/service-discovery/>`_.

BlackBerry OS 10.2
``````````````````

BlackBerry OS up to 10.2.2102 doesn't accept a URL with protocol ``https://`` in front of the server address.
It will always tell you, that it cannot login on your server. So instead of writing:

.. parsed-literal::

    https://|cloudUrl|/remote.php/carddav/principals/username
    
in the server address field, you have to write:

.. parsed-literal::

    |cloudUrl|/remote.php/carddav/principals/username
