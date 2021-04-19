# Win_Paddle_Environment

AiStudio:[Windows-paddle-深度学习环境搭建](https://aistudio.baidu.com/aistudio/projectdetail/1147447)
## 文档内容主要对不熟悉Windows下深度学习环境的小伙伴讲解所需环境的安装，和Linux的差不多，如果有小伙伴安装的时候有任何问题可以在讨论区提出，接下来开始入坑

## 目录	
* 一、下载CUDA	
* 1.2 安装CUDA
* 1.3 添加系统变量	
* 1.4 安装测试	
* 1.5 安装cuDNN	
* 二、安装Anaconda	
* 2.0 Anaconda简介 
* 2.1下载Anaconda	
* 2.2 安装Anaconda 
* 2.3 Anaconda创建环境	
* 2.4 激活环境，配置paddle	
* 2.5 安装paddle2.0	
* 2.6更换下载源	
* 三、安装Pycharm 
* 3.1 下载Pycharm	
* 3.2 安装Pycharm	


#### **相关安装包已经导入到项目中**

#### [地址](https://aistudio.baidu.com/aistudio/projectdetail/1147447)


![](https://ai-studio-static-online.cdn.bcebos.com/0f2ac49af1e843e4b74237f966477c45cb4bf14d683f4825bf77e0eec34da6dd)

# 一、CUDA  cuDNN安装


## 1.1下载CUDA

#### 对于本地使用GPU训练模型的时候光有显卡驱动是不够的，还需要CUDA来支持
#### Windows 环境下，Paddle目前仅支持 CUDA 9.0/10.0 的单卡模式；不支持 CUDA 9.1/9.2/10.1

<br/>

#### **CUDA下载链接：[CUDA](https://developer.nvidia.com/cuda-toolkit-archive)（项目内已上传）**

<br/><br/>

![](https://ai-studio-static-online.cdn.bcebos.com/cc1d5818498f4fa9af71e6525123e98f2576ea28f7f14adb9da0feca0b749c44)

<br/>

#### **选择CUDA Toolkit 10.0 跳转连接后按以下依次选择---下载**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/e24542e9fae2465d947fea6ae016dcf96a19688fcf7b4e51831fd504db52073d)

<br/>
<br/>


#### **nvidia官网访问比较慢并且文件太大，已将下载的安装包上传到本项目中**

<br/>

## 1.2 安装CUDA
#### **打开cuda_10.0.130_411.31_win10.exe安装包**
#### **第一次会提示临时解压路径，完成安装会自动删除，默认/自定义都可以，但不要和安装路径重复，否则会安装失败**

<br/>
<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/3f2d104a03cd49debb572bfab9713bc4cdf8a38d8bdc41a5aa96c466243d6fd2)


<br/>

#### **待解压完成，选择 同意并继续->精简->**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/0e78dd8f4b174153a2f7047e82b9d7c0ae68771bd94e4467a006c3414a9082a3)

<br/>


#### **在这里打对勾，下一步**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/717ba37f646e4c65b73482ad77ab59fdc7a51c60ff644625a415730783d14f1c)

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/10c0b2f07b404b419455b62faf404f309d65c648db504dc089d46a74d3d98a3e)


<br/>

#### **安装完成**

<br/>

## 1.3 添加系统变量


<br/>

#### **依次单击：右键计算机->属性->高级系统设置->高级->环境变量**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/2bd3421d664c4b2da25cbaab19bf5ba17ab7311539f548eba079b788f964086e)


<br/>

#### **在系统环境变量中添加两个变量：**
#### **变量名：**`CUDA_PATH`
#### **变量值：**`C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0`
#### **变量名：**`CUDA_PATH_V10_0`
#### **变量值：**`C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0`

<br/>

#### **注：变量值为CUDA安装地址**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/c114a646bff34f08820a41d62fcbd85a98862ae50c0040b3afbad0252eb3b346)

<br/>

#### **添加完两个变量后，为系统变量的  path  添加2个值：**

```
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\libnvvp
```

![](https://ai-studio-static-online.cdn.bcebos.com/b5a6a579490547d780ff2e2547bd9aab675e6fc5dacb4a939be1906c1e1f9481)

<br/>

#### **修改完成确定**

<br/>

## 1.4 安装测试

<br/>

#### **打开cmd输入nvcc -V 输出以下内容表示CUDA安装成功**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/8754799e6e8c43d5ac5aac0c2415676204ac28fe152d444d808354e94ade5521)


## 1.5 安装cuDNN 
#### **cuDNN压缩包已经上传到项目...**
#### **网址：**[cuDNN](https://developer.nvidia.com/rdp/cudnn-archive)
#### **下载cuDNN需要登录nvidia，或者在本项目中下载**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/53e80454995b4cefa03d3f88c9602c04b408f4608a3a4b3d823f242bf8ca94bc)


<br/>

#### **cuDNN下载完成后，解压，将解压后的三个文件夹复制到C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/63668811b65c4d2d9aeb67e56f8726b651c592ce8a2744f48673724cd986c6cd)

<br/>

#### **Ok,完成**

<br/>

# 二、Anaconda安装

<br/>

#### **Anaconda简介：**
#### **Anaconda指的是一个开源的Python发行版本，其包含了Python、conda等180多个科学包及其依赖项。 因为包含了大量的科学包，Anaconda 的下载文件比较大。**
#### **Anaconda里添加了许多常用的功能包，同时Anaconda还附带捆绑了两个交互式代码编辑器（Spyder、Jupyter notebook），对于初学者很是友好。**

<br/>

## 2.1下载Anaconda

<br/>

#### **网址：**[Anaconda](https://www.anaconda.com/download/)
#### **进入后单击Windows下载（也可以在项目内下载）**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/4a1c2154442c420b9cd25d0fe7318238f8bf0df437af4396862a3e752f3a1881)


<br/>

## 2.2 安装Anaconda

<br/>

#### **下载Anaconda完成后，打开，按提示点击下一步**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/ec397e662d9240bea4ac08a89012711e85441dff6c45465ab7b935956a3b7eb4)

<br/>

#### **用户协议，点击 I Agree**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/6a091b7db68749a68fa287704212200fabeb73ce99614c92a27ec190f28cd30a)

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/5508e201042247f9b528ea7342a24d2601f3e709953c42f0b776ee79b9b7d5a6)

<br/>

#### **路径：建议c盘，也可以单击后面的Browse自己选择安装路径，可能以后在读取速率上有些影响**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/4fc6bcb19cd44e63a26035b6ef7d4d0f677c75cfda1743fca9ccb1f253abba12)


<br/>

#### **选择完路径，下面需要选择添加环境变量，一定要选上，选完后点击install安装，如果忘了勾选可以卸了重装**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/a7e024f49f6b4cb697df032a748b34b767ac8307f5a04988bc899fdcfd262f6d)
![](https://ai-studio-static-online.cdn.bcebos.com/4be9a219fa5342009f20094645e8a5a5730a59eb7edc419588749a945a610605)


<br/>

#### **安装完成，点击next**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/7daa3657d1ed432fac6428eb0a7278d2fd3477d97ee4461e8ee7d5a70b32b78b)

<br/>

#### **这里是pycharm的一个推广，稍后我们会进行安装pycharm，继续点击next**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/10777bbb88a84df0b41ae302670ef61fbcb9b3476e3b4ad5939bf2f7d4a59db1)
![](https://ai-studio-static-online.cdn.bcebos.com/327df96639f74f308c5ad8129f08b8043399449ce16145a29f255673daf666cc)

<br/>

#### **ok，anaconda安装完成**

## 2.3 Anaconda创建环境

<br/>

#### **在左下角搜索地方输入 anaconda，打开 Anaconda Prompt（类似于cmd）**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/1f6ea87fb1b94c609dcc525b0b615742ad905605c9794ace9e740150baa0bed0)

<br/>

#### **打开后界面如下（Skr-Skr-Skr是我的用户名）**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/b775fd9a01fb4c078073ad4bd8d822dc55d85d092ad448b8a46a6dab3bac7b53)

<br/>

#### **输入：**`conda create -n paddle python=3.7`

#### **说明：-n是代表创建的环境名称 python=3.7表示该环境使用3.7版本python**
####  **注：如果出现Collecting package metadata (current_repodata.json): failed错误请查看章节<2.* 更换下载源>**

<br/>

#### **提示会下载以下包：输入y 表示确认**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/306f12d643c34e609e8cbe96cc69d34e0a46d1ba3d684e83bb6f01e499dc7008)

<br/>

#### **等待下载完成**
## 2.4 激活环境，配置paddle

<br/>

#### **更新下conda：**
`conda update --all`

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/6455a7661c76402b98ce4028a2ae1897eb301baa2d604138901e6a5305ef544a)
![](https://ai-studio-static-online.cdn.bcebos.com/8874c5286cc24b9dbc9caea3ae1bcd69c696a02da68e442889d06056a0945e40)

<br/>

#### **更新完成...**

<br/>

## 2.5 安装paddle2.0：

#### **Paddle，我们可以在官网中选择对应环境安装。**
#### 官网链接：[paddlepaddle](https://www.paddlepaddle.org.cn/documentation/docs/zh/install/pip/windows-pip.html)

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/752a81c620b34856bff2d2b5845b7156da65716303c04aabbaa85aaa65916c0c)


#### **上面我们安装的是CUDA10.0 在我们打开的conda环境内输入：**
`python -m pip install paddlepaddle-gpu==2.0.0.post100 -f https://paddlepaddle.org.cn/whl/stable.html`

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/961765763bc54035a29b6f2d4de5628fe07a3a35562f4705add57c8513af9b90)
<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/26c0a8cce03548959f52b52b2afdfe4e090bd91b3a1442398ec55a4a2b4eb749)

<br/>

#### **在我们打开的环境内输入：**
`Python -m pip install paddlepaddle_gpu==2.0.0b0 -f https://paddlepaddle.org.cn/whl/stable.html`

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/6734ba39474844b296f19b531685389004e62a0ef8be441dab95b09734a4dbd1)

<br/>

#### **待安装完成，输入**
`python`
#### **进入命令行后输入** 
```
import paddle
paddle.fluid.install_check.run_check()
```

<br/>

#### **显示Your Paddle Fluid is installed successfully表示paddle安装成功**

![](https://ai-studio-static-online.cdn.bcebos.com/1b3e7d79f0a14b76be133bdef4d8a2ef410fdde1df59490092f3c1dcecb3afc9)

<br/>

#### **注：我们已经安装完paddle的环境，之后使用直接打开conda的paddle环境即可**

<br/>
<br/>

#### **待安装完成，输入**
`python`
#### **进入命令行后输入 **
```
import paddle
paddle.fluid.install_check.run_check()
```
#### 显示Your Paddle Fluid is installed successfully表示paddle安装成功

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/e35d54e296c14f2e810b2a630b01ac1bf9943be6557c47d699eaeb78c5c2edd8)

<br/>

## 2.* 更换下载源
#### **如果在anaconda新建环境的时候产生Collecting package metadata (current_repodata.json): failed错误，是conda下载源问题：**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/255a57c6e0af4e9690ec7e960b5fbf032f02b2ab3885466eb8151e0845e40243)

<br/>

#### **如果出现以上错误，打开用户目录：C:\Users\Skr-Skr-Skr   （Skr-Skr-Skr是我自己的用户名）**
#### **在该目录里面找出.condarc文件（如果没有改文件可以新建一个），使用记事本编辑**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/38e8a8f2cf6740908ea9ab7712065d3e9ba6c570815944438133530c655f256e)

<br/>

#### **在.condarc添加如下内容：**

```
channels:
  - defaults
show_channel_urls: true
channel_alias: https://mirrors.tuna.tsinghua.edu.cn/anaconda
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/pro
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
```

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/bd5fd7fa27f24b3fbf68d96b6eb22cbc93e978a77fd24b2d9c0425bf621f29d6)

<br/>
<br/>


#### **保存后，再次尝试新建环境即可。**

# **三、Pycharm安装**
## **3.1 Pycharm下载**

<br/>

#### **进入官网：**[Pycharm](https://www.jetbrains.com/pycharm/download/#section=windows)
#### **选择下载版本，左边是专业版（收费），右边是社区版**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/a5aa472acecc42f8aa2c496bb7b97f405b55c71c749a403a950b975356b041d6)

<br/>

## 3.2 Pycharm安装

![](https://ai-studio-static-online.cdn.bcebos.com/34df0995a3304c639642ca2d338d25f2cd96f8971e394dc0abc4e6184915e42c)

<br/>

#### **选择安装路径（默认C盘，我的c盘空间有限安装到了D盘）：**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/b6b02121212f4ab2b09c09c8f19ba69e3bf1381e9085438d9513a3c8a4f400dc)

<br/>

#### **4个对勾全选：创建桌面快捷键，添加path环境变量，更新菜单栏，创建关联（py文件默认由pycharm打开）**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/ec02a51a71de409e90858898ca5c4cc39d3819ee7cf6407197d2bf38039b5e4b)

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/b06b6d01250844758061605191082b4d5e762a0b81894fbaa7b5a8a11b4da855)

<br/>

#### **安装完成，提示重启电脑生效，选第二项稍后重启，完成：**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/ad8b3336a37249e982d5f884013ff5855d7a9f778cd14a40bde5cc5044d74523)

<br/>

#### **打开pycharm，选择New，Project：**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/8b374fd2d61f4ea6b693cef08f5706695adeac4610854517bd6266f1016809be)

<br/>

#### **接下来选择：**
**Location：项目位置**

**New environment using：Conda**

**Python version：3.7**

**Creat创建**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/dadae7985d7d4b76b966436959072164424f5a5111814db6986720d98296a13e)

#### **创建完成后，pycharm默认有个main.py**
#### **单击菜单栏 Run-> Run’main.py’**

<br/>

![](https://ai-studio-static-online.cdn.bcebos.com/34d80cf2c49f429580e29d78b5889652c1c473211507429c8e0eb44b95ca3c23)

<br/>

## 完成
#### **以上就是Windws下深度学习环境的配置安装，如果有问题，欢迎在评论区提出**

