.. _extensions:

扩展
==========

扩展是指为 Flask 应用增加功能的包，比如增加发送电子邮件或者连接数据库中的
功能。有些扩展还有助于为应用添加全新的框架，如 ReST API 。


寻找扩展
------------------

Flask 的扩展通常命名为“ Flask-Foo ”或者“ Foo-Flask ” 。许多扩展已经列
入了 `扩展仓库`_ ，由其开发者维护。还可以在 PyPI 搜索标记为
`Framework :: Flask <pypi_>`_ 扩展包。


使用扩展
----------------

请参阅每个扩展的文档以了解其安装、配置和使用说明。一般来说，扩展从
:attr:`app.config <flask.Flask.config>` 获取其自身的配置并在初始化时传递给
应用实例。例如，一个名为“ Flask-Foo ”的扩展使用如下::

    from flask_foo import Foo

    foo = Foo()

    app = Flask(__name__)
    app.config.update(
        FOO_BAR='baz',
        FOO_SPAM='eggs',
    )

    foo.init_app(app)


创建扩展
-------------------

虽然 `扩展仓库`_ 已经包含许多 Flask 扩展，但是如果找不到合适的，
那么可以创建自己的扩展。如何创建扩展请参阅 :ref:`extension-dev` 。

.. _扩展仓库: http://flask.pocoo.org/extensions/
.. _pypi: https://pypi.org/search/?c=Framework+%3A%3A+Flask
