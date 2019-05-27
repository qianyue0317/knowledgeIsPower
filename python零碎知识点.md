1. __new__ 的作用:依照Python官方文档的说法，__new__方法主要是当你继承一些不可变的class时(比如int, str, tuple)， 提供给你一个自定义这些类的实例化过程的途径。还有就是实现自定义的metaclass。
用__new__实现单例是个很重要的知识点
2. debian发行版上边的python-dev包在centos上是python-devel
