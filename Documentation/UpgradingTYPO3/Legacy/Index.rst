.. include:: ../../Includes.rst.txt

.. _index:

==============
Legacy Upgrade
==============

//TODO overview of legacy installation
 - why its considered legacy
 - The new method of upgraing

Minor Upgrades  - Using The Core Updater
========================================

The "Install Tool" in the section "Important Actions" provides a function to
update the TYPO3 Core.

In the section "Important Actions" scroll down to "Core update" and click the
"Check for core updates" button. If the requirements are met, TYPO3 will
automatically install the new source code.

.. note::

   For the Core Updater to work, the following setup is required:

   *  It only works in Unix-like systems (including macOS).

   *  :file:`typo3_src` must be a symlink.

   *  This symlink needs to be writable (and deletable) by the web-server user.

   *  The document root needs to be writable.

   *  One path above document root (:file:`../`) needs to be writable (creation
      of new directories must be allowed).

   *  The :program:`tar` command must be available (for extracting the Source
      package).


.. _install-manually:

Major Upgrades - Symlink The Core
=================================

Go to `http://typo3.org/download/ <http://typo3.org/download/>`_ and download
the source package of the new TYPO3 version.

Extract the package on your web server and, in your TYPO3 document root,
adjust the :file:`typo3_src` symlink.


What's the Next Step?
=====================

In case you performed a *minor update*, e.g. from TYPO3 9.5.0 to 9.5.1, database
updates are usually *not* necessary, though you still have to
:ref:`remove the temporary cache files <remove-temporary-cache-files>`. After
that your update is finished.

.. note::

   Make sure to read the release notes of even the minor versions carefully. While
   great care is taken to keep the minor updates as easy as possible, (especially
   when releasing security updates) more steps might be necessary.

In case of a *major update*, e.g. from TYPO3 8.7 to 9.5, go ahead with the next
step!

Also check out any breaking changes listed in the `changelog
<https://docs.typo3.org/typo3cms/extensions/core/>`_ for the new version.
