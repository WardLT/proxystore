Changelog
#########

Version 0.3.2
-------------

`Released 25 April 2022`

**Summary of Changes**

#. :any:`GlobusStore <proxystore.store.globus.GlobusStore>` improvements:

   * Endpoints parameter supports dict for better serialization (`#e71e96f <https://github.com/gpauloski/proxystore/commit/e71e96ffe2af8ace2da1249744fee71a71d4e221>`_).
   * Files for Globus transfer are now specified rather than recursively discovered (`#c3e69f0 <https://github.com/gpauloski/proxystore/commit/c3e69f05f4a69609ddd9cdefc58beca41dc2434e>`_).
   * Added note on Globus Auth (`Issue #20 <https://github.com/gpauloski/proxystore/issues/20>`_).
   * Added warning on use of `strict` with :any:`GlobusStore <proxystore.store.globus.GlobusStore>` (`Issue #21 <https://github.com/gpauloski/proxystore/issues/21>`_).
   * User home :code:`~/` is now expanded in paths (`Issue #22 <https://github.com/gpauloski/proxystore/issues/22>`_).

#. Fix :code:`RemoteStore.proxy()` logging the incorrect key (`Issue #26 <https://github.com/gpauloski/proxystore/issues/26>`_).
#. Failures to resolve a proxy from a :any:`RemoteStore <proxystore.store.remote.RemoteStore>` now raise an :code:`ProxyResolveMissingKey` exception (`Issue #29 <https://github.com/gpauloski/proxystore/issues/29>`_).
#. Added prototype stat tracking for stores (`PR #33 <https://github.com/gpauloski/proxystore/pull/33>`_).
#. CI/Development changes:

   * Updated development instructions (`Issue #19 <https://github.com/gpauloski/proxystore/issues/19>`_).
   * Added Issue Templates (`Issue #23 <https://github.com/gpauloski/proxystore/issues/23>`_).
   * Added PR Templates (`#deb5e1e <https://github.com/gpauloski/proxystore/commit/deb5e1e34904aec59eec5a9ea31b7acac89142f5>`_).
   * Cleaned up tests (now top-level directory, coverage includes test coverage, etc.) (`#f5f4b57 <https://github.com/gpauloski/proxystore/commit/f5f4b57f6095a7d5f10c328a2e48cfdcf698c002>`_).
   * GitHub actions cleaned up (removed and replaced some) (`PR #31 <https://github.com/gpauloski/proxystore/pull/31>`_).
   * Switch to :code:`setup.cfg` for all configurations (`PR #34 <https://github.com/gpauloski/proxystore/pull/34>`_).
   * Renamed test files for better tab-complete and moved testing infrastructure to :code:`testing/` (`PR #34 <https://github.com/gpauloski/proxystore/pull/34>`_ and `PR #37 <https://github.com/gpauloski/proxystore/pull/37>`_).
   * Use :code:`pre-commit.ci` GitHub action (`PR #37 <https://github.com/gpauloski/proxystore/pull/37>`_).

#. Package name is lowercase proxystore (`PR #34 <https://github.com/gpauloski/proxystore/pull/34>`_).
#. Switched to MIT License (`PR #34 <https://github.com/gpauloski/proxystore/pull/34>`_).


Version 0.3.1
-------------

`Released 17 January 2022`

**Summary of Changes**

#. Cleaned up tests (uniform file names and more mocking of third party libraries).
#. Add :code:`STORES.get_str_by_type()`. (`#bf24158 <https://github.com/gpauloski/ProxyStore/commit/bf2415885a8da47d58af20f1ae0751397a3058e9>`_)
#. Mass changes to CI workflows. See `Issue #16 <https://github.com/gpauloski/ProxyStore/issues/17>`_. (`#1995e90 <https://github.com/gpauloski/ProxyStore/commit/1995e90acf7dc8a5c3ee97dc3db6b4f44112b749>`_)


Version 0.3.0
-------------

`Released 5 January 2022`

**Summary of Changes**

#. :any:`LambdaFactory <proxystore.factory.LambdaFactory>` takes :code:`*args, **kwargs` now. See `Issue #13 <https://github.com/gpauloski/ProxyStore/issues/13>`_. (`#86e6cac <https://github.com/gpauloski/ProxyStore/commit/86e6cac2c782bca7d2ef2e573bd4afc254c4c678>`_)
#. Added source code button to ReadTheDocs. (`#8a20c20 <https://github.com/gpauloski/ProxyStore/commit/8a20c2099e9eea5235b1dc819ef8c633b21ab662>`_)
#. Added :any:`FileStore <proxystore.store.file.FileStore>`. (`#e7f8849 <https://github.com/gpauloski/ProxyStore/commit/e7f8849dfd412cb2a451a624ff1fcd001a4615ca>`_)
#. Added :any:`Store.cleanup() <proxystore.store.base.Store.cleanup>` to store interface for implementations that need to add cleanup logic (such as :any:`FileStore <proxystore.store.file.FileStore>` cleaning up its directory). (`#e7f8849 <https://github.com/gpauloski/ProxyStore/commit/e7f8849dfd412cb2a451a624ff1fcd001a4615ca>`_)
#. Added :any:`GlobusStore <proxystore.store.globus.GlobusStore>` and FuncX+Globus example. (`Issue #15 <https://github.com/gpauloski/ProxyStore/issues/15>`_)
#. The key is now an optional parameter to :any:`Store.set() <proxystore.store.base.Store.set>` and the official get used by the store will be returned by :any:`Store.set() <proxystore.store.base.Store.set>`. :any:`Store.create_key() <proxystore.store.base.Store.create_key>` can be used to specify key generation when a key is not provided. (`#38a78fa <https://github.com/gpauloski/ProxyStore/commit/38a78fad4ec95012923620523c35e9b9c8083828>`_)
#. Better inheritance for subclasses of :any:`RemoteStore <proxystore.store.remote.RemoteStore>` and created the base class :any:`RemoteFactory <proxystore.store.remote.RemoteFactory>` to reduce redundant code in other factory types. (`#cf0a631 <https://github.com/gpauloski/ProxyStore/commit/cf0a631646cbec676928daa6a166218185847fa6>`_)
#. Serialization in ProxyStore is now done to bytes rather than strings. (`#d68ac9d <https://github.com/gpauloski/ProxyStore/commit/d68ac9de92cc5d2b902c2fed462e75df7c830c8e>`_)
#. Added :code:`DEBUG` level logging to :any:`proxystore.store <proxystore.store>`. (`#e0f1052 <https://github.com/gpauloski/ProxyStore/commit/e0f1052a1bae3ccf2af10320852605989b501521>`_)
#. Better testing infrastructure. Generic store tests now use fixtures to test multiple store types so code is not copy/pasted between tests. Added Globus and Parsl mocking to support unittests for :any:`GlobusStore <proxystore.store.globus.GlobusStore>`. (`#91d3894 <https://github.com/gpauloski/ProxyStore/commit/91d3894bd85de8686fda0d9e425f18e122fa9e82>`_)
#. Better handling of timestamps in stores that support mutable objects and strict guarantees. Added :any:`RemoteStore.get_timestamp(key) <proxystore.store.remote.RemoteStore.get_timestamp>`. :any:`FileStore <proxystore.store.file.FileStore>` now uses file modified time. (`#e1bbdb8 <https://github.com/gpauloski/ProxyStore/commit/e1bbdb8d485369e86b1a9acef6ccd2c1321c2e8d>`_)
#. Added the batch methods :any:`Store.set_batch() <proxystore.store.base.Store.set_batch>` and :any:`Store.proxy_batch() <proxystore.store.base.Store.proxy_batch>`. (`#d1d24f7 <https://github.com/gpauloski/ProxyStore/commit/d1d24f76fd8c2e50405d1580f116ac8c7e3d2339>`_)
#. Various docstring and documentation updates.

Version 0.2.0
-------------

`Released 17 May 2021`

**Summary of Changes**

#. Proxies created by :any:`Store.proxy() <proxystore.store.base.Store.proxy>` can auto-evict the data from the store after the proxy has resolved itself using the `evict=True` flag (`#0ef8f61 <https://github.com/gpauloski/ProxyStore/commit/0ef8f617118926737c85936adf2c0355150d93ee>`_).
#. Added cloudpickle to ProxyStore serialization utilities for lambda pickling support (`#a992ec7 <https://github.com/gpauloski/ProxyStore/commit/a992ec756b40551fa36455e39d4bc617cb7cc2ce>`_).
#. Added :any:`LambdaFactory <proxystore.factory.LambdaFactory>` (`#fc7674a <https://github.com/gpauloski/ProxyStore/commit/fc76746a432cfe6f50214bece98ebe956abd848b>`_).
#. Extensive ProxyStore refactor to separate proxy/factory building blocks from the key-value store implementations. See `Issue #8 <https://github.com/gpauloski/ProxyStore/issues/8>`_ and `Pull Request #9 <https://github.com/gpauloski/ProxyStore/pull/9>`_ for more details (`#0564e5f <https://github.com/gpauloski/ProxyStore/commit/0564e5f437cc34097528dd93256460a4bf1e6345>`_).
#. Pass custom factories to :any:`Store.proxy() <proxystore.store.base.Store.proxy>` (`#dffba4c <https://github.com/gpauloski/ProxyStore/commit/dffba4c7b0a81ea12f91d75c1ab014ded435868b>`_).
#. Initialize multiple factories of the same type (`#1411c0f <https://github.com/gpauloski/ProxyStore/commit/1411c0f638e22cdb4ea0047fa97137c84eab8538>`_ and `#41b4bd3 <https://github.com/gpauloski/ProxyStore/commit/41b4bd3c4e432ac00c3b9c3c91fb911fb1450353>`_).


Version 0.1.1
-------------

`Released 28 April 2021`

**Summary of Changes**

#. Added ProxyStore integration into example FuncX and Parsl applications (`#eaa1782 <https://github.com/gpauloski/ProxyStore/commit/eaa1782dedb2436ecbee0d9ea4e11c932720b12a>`_).
#. Added support for preserialized objects (`#c2c2283 <https://github.com/gpauloski/ProxyStore/commit/c2c228316cdfbbd31a3642839bc9b4e9884c2be7>`_).
#. Changed :any:`Proxy <proxystore.proxy.Proxy>` to inherit from the pure Python slots Proxy from `lazy-object-proxy <https://github.com/ionelmc/python-lazy-object-proxy>`_ rather than the C version. Closes `#1 <https://github.com/gpauloski/ProxyStore/issues/1>`_ (`#5c77eb0 <https://github.com/gpauloski/ProxyStore/commit/5c77eb08f6128344aba53f200dad30ddcf035daf>`_).
#. Extensive docstring and documentation updates.
#. Minor unittest updates.

Version 0.1.0
-------------

`Released 21 April 2021`
