.. include:: ../../Includes.rst.txt
.. _index:

====================
Upgrading Extensions
====================

If you have extensions installed, find the corresponding newer
versions you want to install for your new major version, and update them too.

Example::

   composer require typo3/cms-backend:^9.5 typo3/cms-core:^9.5 \
      typo3/cms-extbase:^9.5 typo3/cms-extensionmanager:^9.5 \
      typo3/cms-filelist:^9.5 typo3/cms-fluid:^9.5 typo3/cms-frontend:^9.5 \
      typo3/cms-install:^9.5 typo3/cms-recordlist:^9.5 georgringer/news:^7.0 \
      --update-with-dependencies

.. tip::

   To make selecting the packages easier, you can use the TYPO3 `Composer Helper
   <https://get.typo3.org/misc/composer/helper>`_ to find the packages you need.

To find the matching extension versions you can go to `packagist.org
<https://packagist.org/>`_, search for your extension and take a look at the
"requires" section.

.. tip::

   The list of system extensions developed directly in the TYPO3 core repository
   changes from time to time: Some extensions are merged into others, new system extensions
   are added, and others abandoned or released to the public (and therefore maintained at a
   different place).
   You will find information on the details in this `list
   <https://docs.typo3.org/Home/SystemExtensions.html>`_ or search in the
   `breaking changes <https://docs.typo3.org/c/typo3/cms-core/master/en-us/Index.html>`_
   for the extension key (not the package name!).

.. include:: /Images/ExternalScreenshots/ExtOnPackagist.rst.txt