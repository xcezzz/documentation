Brandable / Generified User Documentation
======================
Added a few reStructuredText substitution directives. Updated images to not be so 'ownCloudy'. User Manual has had many 
things stripped out that honestly should be in the admin manual since an end user would really never have access to the server.
These changes only reside within 'user_manual' since this should be the only one seen by end-users.

#. All **ownCloud** references updated to be |cloudName| 
#. All literal example blocks referencing **example.org/owncloud** or **localhost/owncloud** updated to be parsed literal blocks and now reflect a defined |cloudUrl| ::
  davs://mydefined.domain.com/remote.php/webdav
#. All images updated to remove logos and direct references to **owncloud** or **/owncloud**
#. conf.py rst_epilog updated to inject the substituions from branding.py into every .rst.
#. Makefile updated to not force ``owncloud_org`` ``html_theme`` for ``make html``. Now properly uses the **conf.py** ``html_theme`` var.
#. Theme named **generalized** copied from **owncloud_org**, removed ownCloud.org blue header navigation bar in layout.html.
#. Many other small and miscellaneous changes to **dumb down** the user manual. 
  * An actual **end user** isn't going to be troubleshooting .htaccess files.
  * An end user won't be fixing **big file** issues.
  * Actually why would a real end user wont ever have access to the server itself?

How To Define Branding
--------
branding.py can be updated directly or you can set environment variables CLOUD_NAME and CLOUD_URL for scriptiness::

  cloudName = os.getenv('CLOUD_NAME', u'myCloud')
  cloudUrl = os.getenv('CLOUD_URL', u'cloud.domain.com')

Continue building documentation as usual but for easy copypasta::

  #!/bin/bash
  export CLOUD_NAME="mySuperAwesomeCloud"
  export CLOUD_URL="my.super.awesome.cloud.com"
  make clean && make html && make latexpdf

ownCloud Documentation
======================

This is the ownCloud documentation. It currently focuses on the server,
client manuals are in the respective git repositories. Because of the
complexity of the server and the split into the core and apps modules,
the manuals are in this separate directory.

License
-------

All documentation in this repository is licensed under the Creative Commons
Attribution 3.0 Unported license (`CC BY 3.0`_).

Style
-------

It is using the `Sphinx Documentation Generator
<http://sphinx.pocoo.org/>`_. The syntax follows the `reStructuredText
<http://docutils.sourceforge.net/rst.html>`_ style, and can also be edited
from GitHub.

For PHP documentation you'll need to get the according language
domain package. The documenation for PHP source is located at
http://packages.python.org/sphinxcontrib-phpdomain/reference.html

Manuals
-------

At this point, this repository hosts three manuals:

* **Users Manual:** Covers topics from an end user's Point of View
* **Administrators Manual:** Setup, Deployment, Best Practices, etc.
* **Developers Manual:** Developing Apps for ownCloud & understanding the
  core Architecture.

Building
--------

Linux / OS X
^^^^^^^^^^^^

First, make sure that the following are installed:

* Python 2 (2.6.0 or better, Python 3 is not yet supported!)
* Sphinx (e.g. ``sudo yum install python-sphinx``),
  on Mac: ``sudo easy_install Sphinx``
* Sphinx PHPDomain (e.g. ``sudo easy_install sphinxcontrib-phpdomain``)
* rst2pdf (e.g. ``sudo easy_install rst2pdf``)
* If you're on Arch Linux, the build script is called sphinx-build2 which
  will fail. You will need to provide a link to the expected script name::

     sudo ln -s /usr/bin/sphinx-build2 /usr/bin/sphinx-build

...then enter any manual directory, then run ``make html``. The result can
be found in the ``_build/html`` subdirectory.  PDFs can be build with the
``make latexpdf`` command and found

Windows
^^^^^^^

Running ``setup.cmd`` will install Python 2.7 and install all dependencies.

Enter any manual and clicking the "Build HTML" shortcut will create a HTML
build. Likewise, "Build PDF" will build the PDF using the more lightweight,
but feature-incomplete RST2PDF tool. The results are in ``_build/html`` and
``_build/pdf`` respectively.

Importing Word and OpenDocument files
-------------------------------------

Sometimes, existing documentation might be in Word or LibreOffice documents. To
make it part of this documentation collection, follow these steps:

Prerequisits
^^^^^^^^^^^^

1. Install Python 2.x
2. Install odt2shpinx (``easy_install odt2sphinx``)
3. Install GCC/clang (`Xcode command line tools`_ required on Mac OS)

Process
^^^^^^^

1. ``doc/docx`` files need to be stored as odt first
2. Run ``odt2sphinx my.docx``
3. Move the resulting ``rst`` files in place and reference them
4. Wrap text lines at 80 chars, apply markup fixes

.. _CC BY 3.0: http://creativecommons.org/licenses/by/3.0/deed.en_US
.. _`Xcode command line tools`: http://stackoverflow.com/questions/9329243/xcode-4-4-and-later-install-command-line-tools
