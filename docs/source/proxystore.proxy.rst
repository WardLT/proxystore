proxystore.proxy
################

.. automodule:: proxystore.proxy
   :members:
   :inherited-members:
   :show-inheritance:

.. class:: proxystore.proxy.Proxy(factory: proxystore.factory.Factory)

   Lazy Object Proxy

   An extension of the Proxy from `lazy-object-proxy <https://github.com/ionelmc/python-lazy-object-proxy>`_ with modified pickling behavior.

   An object proxy acts as a thin wrapper around a Python object, i.e. the proxy behaves identically to the underlying object.
   The proxy is initialized with a callable factory object.
   The factory returns the underlying object when called, i.e. ‘resolves’ the proxy. The proxy does just-in-time resolution, i.e., the proxy does not call the factory until the first access to the proxy (hence, the lazy aspect of the proxy).

   The factory contains the mechanisms to appropriately resolve the object, e.g., which in the case for ProxyStore means requesting the correct object from the backend store.

   .. code-block:: python

      >>> x = np.array([1, 2, 3])
      >>> f = ps.factory.SimpleFactory(x)
      >>> p = ps.proxy.Proxy(f)
      >>> assert isinstance(p, np.ndarray)
      >>> assert np.array_equal(p, [1, 2, 3])

   .. note::

      The `factory`, by default, is only ever called once during the lifetime of a proxy instance.

   .. note::

      When a proxy instance is pickled, only the `factory` is pickled, not the wrapped object.
      Thus, proxy instances can be pickled and passed around cheaply, and once the proxy is unpickled and used, the `factory` will be called again to resolve the object.

   :param factory: callable object that returns the underlying object when called.
   :type factory: :class:`Factory <proxystore.factory.Factory>`

   :raises TypeError: if `factory` is not an instance of :class:`Factory <proxystore.factory.Factory>`.
