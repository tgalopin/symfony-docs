.. index::
   single: Cache

Cache
=====

Nowadays, performance is taking more and more importance during the development of modern web applications.
To help you easily create fast applications, Symfony provides a powerful caching system based on the PSR-6
standard.

.. versionadded:: 3.1
   The Cache component was introduced in Symfony 3.1.

.. note::

   The Symfony Cache component is a standalone library that can be used outside
   of Symfony projects. For more information, see the
   :doc:`Cache component documentation </components/cache>`.

.. note::

   This documentation is about backend cache (putting items in cache from Symfony). If you want to speed up
   your application, you should also consider adding :doc:`HTTP Cache </http_cache>`.

Application cache and system cache
----------------------------------

When we talk about cache in Symfony, we need to distinguish two types of cache having a different lifetime:

#. **Your application cache** (your custom models cache), which is written at runtime and which needs to be
   shared amongst your different application servers to avoid synchronization issues ;

#. **The system cache** (Symfony and all installed bundles cache), which is built at compile time (when you
   will run the ``cache:clear`` command) and which should not be shared amongst application servers ;

Because of this difference, Symfony provides two services for cache to let you configure shared cache independantly
from system cache.

Configuring caches storage
--------------------------

By default, both your application cache and the system cache are stored on your local filesystem (in the ``var/cache``
directory) but several other

``` yaml
# config.yml

framework:
   cache:
      app: cache.adapter.filesystem
```
