<!--
 * @Author: chang_an
 * @Date: 2019-12-13 11:07:45
 * @LastEditors  : chang_an
 * @LastEditTime : 2019-12-18 19:29:39
 * @FilePath: \install\README.md
 -->
## 1. 安装Anaconda  
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

## 2. 安装 VS Code
进入Anaconda后，安装VS code

![安装 VS code](https://github.com/Gemini128663/photos/blob/master/install_vscode.png)

## 3. 安装git

- 下载git

  https://git-scm.com/download/win
  打开即可自动下载，默认安装方式，点击next即可。

- 配置git

  打开Git Bash  输入以下命令进行配置

  ```git config --global user.name "your name"```

  ```git config --global user.email "your email address"```

## 4. 用git连接VS code和github

1. 创建github账户。

2. 本地提交使用免密登录(SSH):
   1. 关于HTTPS和SSH的区别，网上有很多，我就不阐述了。
   2. Git Bash中输入 ssh-keygen -t rsa -C "your email address"，一直回车即可可生成一个.ssh文件。

   3. 在生成的.ssh文件中用记事本方式打开id_rsa.pub文件，复制。

   4. 打开github,点击右上角个人信息
      1. 根据以下视图操作
      ![第一步](https://github.com/Gemini128663/photos/blob/master/1.png)
      ![第二步](https://github.com/Gemini128663/photos/blob/master/2.png)
      ![第三步](https://github.com/Gemini128663/photos/blob/master/3.png)
      ![第四步](https://github.com/Gemini128663/photos/blob/master/4.png)
      完成之后，公钥添加完毕。

3. 新建仓库

    ![新建仓库](https://github.com/Gemini128663/photos/blob/master/5.png)

    ![six](https://github.com/Gemini128663/photos/blob/master/6.png)

    仓库创建后，选择 Use SSH

    ![seven](https://github.com/Gemini128663/photos/blob/master/7.png)

    ![eight](https://github.com/Gemini128663/photos/blob/master/8.png)
   
4. 打开VS code
   1. Ctrl+Shift+p，搜索Git:clone，粘贴地址。

   2. 选择存储位置。
   3. 修改文件。
   4. 上传到github:  
    ![ten](https://github.com/Gemini128663/photos/blob/master/10.png)
    ![eleven](https://github.com/Gemini128663/photos/blob/master/11.png)
    ![twelve](https://github.com/Gemini128663/photos/blob/master/12.png)
    ![thirteen](https://github.com/Gemini128663/photos/blob/master/13.png)即可将更改的文件推送到github上。
### 待更新



