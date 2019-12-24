<!--
 * @Author: chang_an
 * @Date: 2019-12-13 11:07:45
 * @LastEditors  : chang_an
 * @LastEditTime : 2019-12-24 08:26:55
 * @FilePath: \install\README.md
 -->

# 1.安装Anaconda、VS code、git

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

```python

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

![安装 VS code](https://github.com/Gemini128663/photos/raw/master/photos/install_vscode.png
)

## 3. 安装git

- 下载git

  <https://git-scm.com/download/win>
  打开即可自动下载，默认安装方式，点击next即可。

- 配置git

  安装完成之后右键打开Git Bash  输入以下命令进行配置

  ```git config --global user.name "your name"---(github用户名)```

  ```git config --global user.email "your email address"---(github邮箱地址)```

## 4. 用git连接VS code和github

1. 创建github账户。

2. 本地提交使用免密登录(SSH):
   1. 关于HTTPS和SSH的区别，网上有很多，这里就不阐述了。
   2. Git Bash中输入 ssh-keygen -t rsa -C "your email address"，一直回车即可可生成一个.ssh文件。

   3. 在生成的.ssh文件中用记事本方式打开id_rsa.pub文件，复制。

   4. 打开github,点击右上角个人信息

       根据以下视图操作  

        1.  
        ![第一步](https://github.com/Gemini128663/photos/raw/master/photos/1.png
)  

        2.  
        ![第二步](https://github.com/Gemini128663/photos/raw/master/photos/2.png
)  

        3.  
        ![第三步](https://github.com/Gemini128663/photos/raw/master/photos/3.png)  

        4.  
        ![第四步](https://github.com/Gemini128663/photos/raw/master/photos/4.png
)  

      完成之后，公钥添加完毕。

3. 新建仓库  
   1.  
   ![新建仓库](https://github.com/Gemini128663/photos/raw/master/photos/5.png
)  
   2.  
   ![six](https://github.com/Gemini128663/photos/raw/master/photos/6.png
)  
   3.  
   ![seven](https://github.com/Gemini128663/photos/raw/master/photos/7.png
)  
   4.  
   ![eight](https://github.com/Gemini128663/photos/raw/master/photos/8.png
)  

    仓库创建后，选择 Use SSH，复制地址。

4. 打开VS code
   1. Ctrl+Shift+p，搜索Git:clone，粘贴地址。
   2. 选择存储位置。
   3. 修改文件。
   4. 上传到github:  
      1.  
      ![ten](https://github.com/Gemini128663/photos/raw/master/photos/10.png
)  
      2.  
      ![eleven](https://github.com/Gemini128663/photos/raw/master/photos/11.png
)  
      3.
      ![twelve](https://github.com/Gemini128663/photos/raw/master/photos/12.png
)  
      4.  
      ![thirteen](https://github.com/Gemini128663/photos/raw/master/photos/13.png
)  

    即可将更改的文件推送到github上。

 上传到Pypi

# 2. 上传模块到Pypi

 1. 首先在与代码文件夹同级目录新建setup.py文件，内容如下：其中，前三个是必须要写的。其他的参数请参考官方文档：<https://packaging.python.org/tutorials/packaging-projects/>
 2. 当然是创建一个Pypi的账号了，至于怎么创建我就不用说了吧。Pypi传送门：<https://pypi.org/>
 3. 在setup.py目录下打开终端，输入
```python setup.py sdist bdist_wheel```,会生成库名称.egg-info文件夹、build文件夹、dist文件夹（包括压缩文件和whl文件）三个文件夹
 4. 在同样的终端下输入```python -m twine upload -u Pypi用户名 -p 密码 dist/*```将dist文件夹上传到Pypi(依赖twine模块 下载：```pip install twine```)

\# 这里有几个想给大家说下我自己上传过程中遇到的几个问题

1. 工作都是在setup.py终端下的，不用其他的。
2. 尽量库的名称与存放代码文件夹的名称相同。
3. 上传好了一定要自己下载测试一下。

以上几个都是我在上传过程中遇到的问题，如果在上传测试中遇到什么问题，我们可以一起讨论。

联系方式

邮箱:1286631591@qq.com

# 3. 关于git

- Git有三种状态：已提交(committed)、已修改(modified)和已暂存(staged)。已提交表示数据已经安全的保存在本地数据库中。已修改表示修改了文件，但还没有保存到数据库中。已暂存表示对一个已修改文件的当前版本做了标记，使之包含在下次提交的快照中。由此引入git项目的三个工作区域的概念：**Git仓库、工作目录以及暂存区域**。
  - Git仓库是Git用来保存项目的元数据和对象数据库的地方。这是Git中最重要的部分，从其他计算机克隆仓库时，拷贝的就是这里的数据。
  - 工作目录是对项目的某个版本独立提取出来的内容。这些从Git仓库的压缩数据库中提取出来的的文件。放在磁盘上供你使用或者修改。
  - 暂存区域是一个文件，保存了下次将提交的文件列表信息，一般在Git仓库目录中。有时候也被称作“索引”，不过一般说法还是叫暂存区域。
  
- 基本的Git工作流程如下：
  1. 在工作目录中修改文件

  2. 暂存文件，将文件的快照放入暂存区域

  3. 提交更新，找到暂存区域的文件，将快照永久性存储到Git仓库目录。

如果Git目录中保存着特定版本的文件，就属于已提交状态。如果作了修改并已放入暂存区域，就属于已暂存状态。如果自上次取出后，作了修改但还没有放到暂存区域，就是已修改状态。

## GIt基础-获取Git仓库

### 获取Git仓库

有两种取得Git项目仓库的方法。第一种是在现有项目或目录下导入所有文件到Git中；第二种是从一个服务器克隆一个现有的仓库。

#### 在现有目录中初始化仓库

如果打算使用Git对现有的项目进行管理。需要进入该项目目录并输入：
```git init```

#### 克隆现有的仓库

从Git远程仓库中将每一个文件的每一个版本拉取下来。
```git clone url```
这会在本地clone一个文件夹。
## GIt基础-记录每次更新到仓库
```git add``` 是一个多功能命令

1. 可以开始跟踪新文件
2. 或者把已经跟踪的文件放到暂存区
3. 还能把用于合并时把有的冲突的文件标记为已解决状态。


如果是新建文件，要使用```git add 文件名字``` 跟踪文件。(-U表示未被跟踪的文件)

```git commit -m "XXXXX"```是将已暂存的文件永久性存储到Git仓库目录。

之后如果只是修改文件，就可以使用 ```git commit -am "XXXXXX"```会自动把所有已经跟踪过的文件暂存器来一起提交，从而跳过git add 步骤。

如果想把项目推送到远程仓库，则还需要``git push``命令.
- 总结以上，一个流程所使用的的命令有
  - git clone &#8195;**将远程仓库中将每一个文件的每一个版本拉取下来**
  - git add . &#8195;**跟踪所有新文件且将已修改的所有文件放到暂存区**
  - git commit -m "XXXX"&#8195;**将暂存区域的文件永久的存放到Git仓库**
  - git push  &#8195;**将仓库推送到远程仓库**

\# git的其他使用以及其他命令请参考 <https://git-scm.com/book/en/v2/>


