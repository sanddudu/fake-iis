fake-iis
========

让你的Nginx变成IIS的样子

源码来自 Nginx 1.5.10

**警告：nginx 爆出 SPDY 堆缓冲溢出漏洞，影响 nginx 1.3.15-1.5.11 ，如果您的 nginx 也是 1.5.10 ，请升级至 1.5.11 或打此 patch： [http://nginx.org/download/patch.2014.spdy2.txt](http://nginx.org/download/patch.2014.spdy2.txt)**

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
* 同版本：将patch文件放到源代码文件夹中，执行`patch -p1 < fake-iis.patch` ，然后自行选择全新安装还是替换安装，最后将 `html` 文件夹里的 `index.html` （可选） 拷贝到 nginx 安装目录下
* 不同版本不推荐使用该方法安装，步骤与同版本相同

许可证
--------
由于修改自 nginx ，许可证也使用 2-Clause 类BSD 许可证。

自定义
--------
默认将nginx的版本号修改为 10.0 InDev ，可以自行修改 `nginx.h` 文件进行修改  
`ngx_http_special_response.c` 文件里是 HTTP 状态码的返回页面，可以根据格式自行修改代码

Q&A
--------
Q：为什么要做这个东西？  
A：~~恶趣味爆发~~
