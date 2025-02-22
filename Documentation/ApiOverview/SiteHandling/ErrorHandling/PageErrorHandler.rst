.. include:: /Includes.rst.txt
.. index:: pair: Error handling; Page
.. _sitehandling-errorHandling_page:

========================
Page-based error handler
========================

The page error handler displays the content of a page in case of a certain
HTTP status. The content of this page is generated via a TYPO3-internal
sub-request.

The page-based error handler is defined in
`\TYPO3\CMS\Core\Error\PageErrorHandler\PageContentErrorHandler
<https://github.com/typo3/typo3/blob/master/typo3/sysext/core/Classes/Error/PageErrorHandler/PageContentErrorHandler.php>`__.

FeatureFlag: `subrequestPageErrors`
-----------------------------------

The internal sub-request is the default behavior. This behavior can be disabled
in favor of a curl-based approach by using the feature flag `subrequestPageErrors`
in the :guilabel:`Settings` module.

In order to prevent possible denial-of-service attacks when the page-based error
handler is used with the curl-based approach, the content of the error page is
cached in the TYPO3 page cache. Any dynamic content on the error page (for
example content created by TypoScript or uncached plugins) will therefore also be
cached.

If the error page contains dynamic content, TYPO3 administrators must
ensure that no sensitive data (for example username of logged in frontend user)
will be shown on the error page.

If dynamic content is required on the error page, it is recommended
to implement a :ref:`custom PHP based error
handler<sitehandling-customErrorHandler>`.

Properties
==========

The page-based error handler has the properties
:ref:`sitehandling-errorHandling_errorCode` and
:ref:`sitehandling-errorHandling_errorHandler` and the following:

errorContentSource
------------------

:aspect:`Datatype`
    string

:aspect:`Description`
   May be either an External URL or TYPO3 Page that will be fetched with
   curl and displayed in case of an error.

:aspect:`Example`
    `t3://page?uid=123`

Examples
========

Internal error page
-------------------

Show the internal page with uid 145 on errors with HTML status 404.
The content of this page will be fetched via internal sub-request.

.. code-block:: yaml

   errorHandling:
     -
       errorCode: 404
       errorHandler: Page
       errorContentSource: 't3://page?uid=145'

External error page
-------------------

Shows an external page on all errors with a HTML status not otherwise defined.

.. code-block:: yaml

   errorHandling:
     -
       errorCode: 0
       errorHandler: Page
       errorContentSource: 'https://typo3.org/404'
