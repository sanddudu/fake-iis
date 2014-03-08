fake-iis
========

让你的Nginx变成IIS的样子

源码来自 Nginx 1.5.10

特点
--------
* 修改了源代码，将nginx返回的服务器和错误页改成了IIS

使用方法
--------
###全新安装
* 同版本：将相关文件替换原代码包中的文件，然后 `make && make install`
* 更高或更低版本：将相关文件进行比对后替换相应部分代码，然后 `make && make install`

###替换安装
* 同版本：将相关文件替换原代码包中的文件，然后 `make` ，备份好原来的 nginx 文件，将 `objs` 文件夹里的 `nginx` 和 `html` 文件夹里的 `index.html` （可选） 拷贝到 nginx 安装目录下
* 更高或更低版本：将相关文件进行比对后替换相应部分代码，然后 `make` ，备份好原来的 nginx 文件，将 `objs` 文件夹里的 `nginx` 和 `html` 文件夹里的 `index.html` （可选） 拷贝到 nginx 安装目录下

###通过patch安装
* 同版本：将patch文件放到源代码文件夹中，执行`patch -p1 fake-iis.patch`
* 不同版本不推荐使用该方法安装

许可证
--------
由于修改自 nginx ，许可证也使用 2-Clause 类BSD 许可证。

Q&A
--------
Q：为什么要做这个东西？  
A：~~恶趣味爆发~~