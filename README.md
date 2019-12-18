<!--
 * @Author: chang_an
 * @Date: 2019-12-13 11:07:45
 * @LastEditors  : chang_an
 * @LastEditTime : 2019-12-18 19:29:39
 * @FilePath: \install\README.md
 -->
#### 1. 安装Anaconda  
Anaconda指的是一个开源的 Python 发行版本，其包含了conda、Python 等180多个科学包及其依赖项。通过安装 Anaconda ，能够大量减少配置Python环境的时间，减少许多不必要的麻烦。  
- 下载 Anaconda   
进入Anaconda官方网站 <https://www.anaconda.com/distribution> 下载相对的版本。  
![图片点击请查看](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/OpenCV-Python%E5%BC%80%E5%8F%91%E6%89%8B%E5%86%8C/anaconda.png)  
选择 Python3.7 , 64 位版下载。  

- 安装 Anaconda  
在 Anaconda 的安装过程中，一般都是点击下一步就可以了。但有个地方要注意：
![安装Anaconda](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/OpenCV-Python开发手册/install_anaconda.png
)    
画红圈的地方要勾选，将 Anaconda 添加到环境变量。

- 为Anaconda配置清华镜像源  
Anaconda 默认的镜像源都在国外，访问不但速度慢，而且经常不稳定。在国内使用的话，把 Anaconda 的镜像源配置为清华镜像源，不仅访问稳定，而且下载速度快，非常适合下载安装 Python 的各种函数库。  
在cmd下运行命令：conda config --set show_channel_urls yes，在用户目录下生成 .condarc 文件。  
修改.condarc文件里面的内容：

```

channels:
  - defaults
show_channel_urls: true
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
```
