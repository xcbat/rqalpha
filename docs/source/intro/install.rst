.. _intro-install:

==================
安装指南
==================

兼容性
==================

RQAlpha目前只支持 python 3.4+ && Python 2.7+

安装前
==================

我们强烈建议您在安装 RQAlpha 前，首先单独安装 bcolz 库，因为其编译时间较长，并且中间比较容易失败，单独安装好以后再继续安装RQAlpha。

Windows 环境下编译安装 bcolz 需要使用Visual C++ Compiler，需要自行下载并安装 visual-cpp-build-tools，

如果觉得麻烦，也可以直接去 http://www.lfd.uci.edu/~gohlke/pythonlibs/#bcolz 下载相应版本的 bcolz wheel 包，直接安装编译后的 bcolz 版本。

安装
==================

为了避免一些安装问题，建议您先升级您的 pip 和 setuptools ::

    $ pip install -U pip setuptools

因为 bcolz 对于一些用户可能会安装困难，可能需要重试多次，所以建议先安装 cython / bcolz 库::

    $ pip install cython
    $ pip install bcolz==1.1.0

安装 RQAlpha ::

    $ pip install rqalpha

如果执行 `pip install` 安装依赖库网络速度比较慢的话，推荐使用国内镜像来进行加速::

    $ pip install -i https://pypi.tuna.tsinghua.edu.cn/simple rqalpha

查看 RQAlpha 是否安装成功可以通过如下方式::

    $ rqalpha version

.. _intro-install-get-data:

获取回测数据
==================

RiceQuant 免费提供日级别的股票和期货数据供回测使用，可以通过以下命令来进行每日数据的增量更新::

    $ rqalpha update_bundle

bundle 文件默认存放在 `~/.rqalpha` 下，您也可以指定 bundle 文件的存放位置，

.. code-block:: bash

    $ rqalpha update_bundle -d target_bundle_path

如果您使用了指定路径来存放 bundle，那么执行程序的时候也同样需要指定对应的 bundle 路径。

.. code-block:: bash

    $ rqalpha run -d target_bundle_path .....

详细参数配置请查看 :ref:`api-config`
