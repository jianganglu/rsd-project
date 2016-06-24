# rsd-project
静态资源缓存控制编译工具

#第一步：安装工具

这个命令行小工具依赖 nodejs 环境，因此，请先确保本地安装了它。
使用 nodejs 随带的 npm 包管理工具进行安装：

    npm install -g rsd
    
#第二步：创建项目

在 命令行 下clone本仓库，或者自己创建一个新的项目，并进入：

    mkdir rsd-project  # 项目名任意 cd rsd-project
    
在项目根目录下创建一个空的 fis-conf.js 文件，这是工具配置，什么都不用写，空着就行。

然后开始在项目目录下，随意创建或添加 页面、脚本、样式、图片、字体、音频、视频等等前端资源文件，正常写前端代码吧！

#第三步：发布代码

在项目根目录下执行：

    rsd release --md5 --dest ../output
  
然后去到 ../output 目录下去查看一下产出结果吧，所有静态资源都以md5摘要形式发布了出来，所有资源链接，我说 所有链接，包括html中的图片、样式、脚本以及js中的资源地址、css中的资源地址全部都加上了md5戳。

上述命令中，--md5 就是表示要给所有资源定位标记加上摘要信息的意思，不加这个参数就没有摘要信息处理。--dest ../output 表示把代码发布到当前目录上一级的output目录中。整个这条命令还可以简写成：

    rsd release -m -d ../output
    
或者进一步连写成：

    rsd release -md ../output
    
#在本地服务器中浏览发布代码

你本地安装了诸如 Apache、Nginx、Lighttpd、IIS等服务器么？如果安装了，假设你的服务器 根目录 在 d:\wwwroot，你可以利用rsd工具的release命令，把代码发布过去，比如：

    rsd release -md d:\wwwroot
    
这样就把代码发布到了本地服务器根目录下，然后就可以在浏览器中查看效果了！

如果你本地没有安装任何服务器，你可以使用rsd内置的调试服务器，执行命令：

    rsd server start
    
接下来我们同样要把代码发布到这个内置服务器中，release命令如果省略 --dest <path>参数，就表示把代码发布到内置服务器的根目录下：

    rsd release -m
    
在浏览器中访问： http://localhost:8080 即可

[静态资源缓存控制编译工具](http://www.open-open.com/lib/view/open1414742344184.html)
