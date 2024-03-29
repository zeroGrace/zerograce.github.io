---
layout: post
title:  服务器配置记录-anaconda & vscode密钥连接
date:   2023-12-30
categories: server
tag: connection
---

* content
{:toc}


服务器linux系统及版本：Pop!_OS 22.04 LTS； 连接工具：finalshell, vscode

一些注意事项和建议:

1. finalshell文件部分的图形界面有延迟，一般进行文件操作后（删除、新建、上传文件等），都需要手动右键刷新。有时时间较长，需要耐心一点多刷新几次，不要急着进行后续操作。

2. linux下大多数命令的原则是“无返回信息即为操作成功”，如果有问题则会反馈报错信息。最初使用时可能误以为是指令没反应，实际情况下指令大概率已成功运行。

3. linux系统命令行界面输入指令时，**不要习惯性使用windows常用的复制粘贴快捷键操作来输入命令**（如ctrl+c复制、crtl+v粘贴等；命令行下，**<u>ctrl+c：中断当前运行程序</u>**）。

   （linux系统命令行界面不包括finalshell在下方提供的命令输入栏。在这一命令输入栏中输入指令时，快捷键可正常使用，也可选择历史命令。推荐在输入栏中敲命令）

4. 遇到问题时，参考的解决方案首选从对应的（英文）官网上找，建议google+英文关键词搜索，实在没有或过于繁杂，再搜中文

5. 尽量多写过程记录、报错记录及处理方案，特别是针对系统的操作；以及输入指令前大致弄清指令的含义和作用。

## finalshell账号密码连接服务器

1. 打开finalshell连接管理器，点击左上角最左的“文件+”图标，在编辑连接窗口添加相关信息。

   - 名称：自定；
   - 主机（IP）、端口：server管理员提供、指定
   - 用户名、密码：自己的server账户

2. 文件上传、下载、删除：上传下载可直接在finalshell文件界面的部分右键；删除文件时，右键删除可能会有延迟甚至卡死，最好使用命令行删除：

   ```shell
   # file_path: 要删除的文件所在文件夹路径；file_name：要删除的文件名
   # 切换至待删文件所在文件夹
   cd file_path 
   # 删除文件
   rm -rf file_name
   ```


## 从头开始配Anaconda环境

1. 安装python和anaconda（仅需安装Anaconda3）

   以下提供的是最笨但过程比较清晰保险的办法，可以直接通过linux命令行下载安装程序，或直接移植他人的环境。

   - 下载：在官网（需科学上网），或在[清华开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/)下载Anaconda3安装文件

     ![image-20231229160714702](/styles/images/pics/image-20231229160714702.png)

   - 将下载好的.sh安装文件通过finalshell上传至服务器，放在自己的根目录（~）

      ```shell
      # 切换到.sh安装文件所在的用户根目录（~）
      cd ~
      # 安装（bash后是安装文件名）
      bash Anaconda3-2023.03-0-Linux-x86_64.sh
      ```
   
   然后一路回车或yes即可
   
2. 检查conda是否安装成功：

   ```python
   conda info
   ```

   如果显示了信息，证明conda已安装成功。

   如conda info失败（可能是安装过程中间漏了yes，没有自动初始化并进入base环境），可尝试以下命令：（参考[官网教程]( https://docs.anaconda.com/free/anaconda/install/linux/ ) ）

   ```shell
   source /home/yangsiyue/anaconda3/bin/activate
   conda init
   ```

   用户账户前出现`(base)`字样则成功。   

3. （可选，建议先跳过）conda换源，换镜像，防止被墙、提速。（个人测试来看目前不换源安装并无问题，校园网下安装大多数python包时均较快，且没有额外麻烦。可以遇到问题时再考虑换源）：

   参考：Xinze Blog，[Add internal mirrors for conda, pip, brew, ubuntu, and other multiple tools](https://xinzezhang.github.io/2020/08/12/mirrors/)

   方式：

   - 新建`.condarc`文件(在当前用户的主目录下；同时也是Anaconda的安装目录)

     ```shell
     touch ~/.condarc
     ```

   - 将以下镜像复制到`.condarc`内：

     ```shell
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

4. 创建conda虚拟环境

   ```shell
   # enviro_name:所创建的conda虚拟环境的名称（自己命名）
   # python版本最好3.8及以上
   conda create --name enviro_name python=3.10
   ```

5. 激活并切换至所创建的虚拟环境

   ```shell
   # 老版本conda
   conda activate enviro_name

   # 新版本conda
   source activate enviro_name
   ```

6. 安装常用的python package（按个人需求）：

   ```shell
   # xlrd和openpyxl是pandas读写excel文件必需的包，最好先装；
   # 安装sklearn和pandas之前最好先装numpy
   conda install xlrd
   conda install openpyxl
   conda install numpy
   conda install pandas
   conda install matplotlib
   conda install scikit-learn
   conda install scipy
   ```

7. 安装可在GPU（cuda）上运行的pytorch:

   1. 打开[pytorch官网]( https://pytorch.org/get-started/locally/ )，选择以下配置：

      ![image-20231229164454366](/styles/images/pics/image-20231229164454366.png)

   2. 复制并在命令行里输入网页提供的代码：

      ```shell
      conda install pytorch torchvision torchaudio pytorch-cuda=12.1 -c pytorch -c nvidia
      ```

   3. 测试是否安装成功：

      ```python
      # 进入python命令行模式（直接命令行里输python)
      python
      # 前缀变成>>>后输入以下代码
      # 导入模块
      import torch
      # 查看cuda是否可用（返回True即为正常可用）
      torch.cuda.is_available()
      # 退出python命令行模式
      exit()
      ```

8. 列出并查看当前环境下所有的package及其版本

   ```shell
   conda list
   ```

9. 退出（关闭）当前conda环境。
   
   注：如果是非base的conda环境（自己新建的），且此前同时activate了base环境，则可能需要运行2次上述代码，一次是从自己的环境退出到base，再一次从base退出到系统。

   ```shell
   conda deactivate 
   ```

10. 查看所有conda环境

    ```shell
    #当前操作所在环境前以*标示
    conda env list
    ```

11. 删除某个conda环境及其中安装的所有包：([其他remove操作](https://docs.conda.io/projects/conda/en/latest/commands/remove.html))

    ```shell
    conda remove -n enviro_name --all
    ```

## vscode远程密钥连接与代码操作

代码及数据文件通过finalshell上传服务器后，希望利用本地（自己笔记本电脑上）的vscode进行编辑、修改、运行等操作。所需操作步骤如下：

1. 本地安装ssh客户端（就是finalshell，直接windows cmd中输ssh检查本地是否有ssh，显示无误即可直接进行下一步）

2. 生成ssh密钥，在服务器端上传公钥，检查私钥-公钥连接方式。

   1. 本地生成并保存ssh密钥。ssh密钥为一对私钥(id_rsa)-公钥(id_rsa.pub)，通常保存在本地`C:\Users\admin\.ssh`路径下（admin对应windows用户名）。生成密钥的方法很多，putty, git bash等均可。

   2. 服务器端，在根目录下创建.ssh目录和authorized_keys文件

      ```shell
      # 创建 .ssh 目录
      mkdir -p ~/.ssh 
      # 创建 authorized_keys 文件
      touch ~/.ssh/authorized_keys 
      ```

   3. 将公钥（id_rsa.pub）文件通过finalshell上传到服务器端.ssh文件夹中。

   4. 复制id_rsa.pub文件内容并将其加入到authorized_key文件中

      ```shell
      # 从根目录切到.ssh目录下
      cd .ssh
      # 将公钥文件内容复制到authorized_key文件内
      cat id_rsa.pub >> authorized_keys
      ```

   5. 检查连接：finalshell退出账号密码连接，改用公钥-私钥连接

      -  点“私钥”后方“浏览”，上传本地.ssh文件夹中的id_rsa文件。
      -  finalshell测试连接，连接成功说明公钥-私钥连接配置成功。

   6. finalshell上传代码文件夹（注意所有文件夹命名遵循代码变量命名原则，不要掺杂其他字符或中文）

3. vscode配置

   1. vscode在扩展商店中搜“remote”，点install安装`Remote Development extension pack`或`Remote - SSH`。前者包括后者及其他一些包。安装后侧边栏出现图标 ![image-20231229190349944](/styles/images/pics/image-20231229190349944.png) ，左下角显示 ![image-20231229190459226](/styles/images/pics/image-20231229190459226.png)

      ![image-20231229185423878](/styles/images/pics/image-20231229185423878.png)

   2. 点侧边栏的 ![image-20231229190349944](/styles/images/pics/image-20231229190349944.png) 图标，点SSH右侧的齿轮图标，会弹出菜单选择要编辑的配置文件，选本地`.ssh`下的`config`文件（通常为第一个）。

   3. 打开文件后，修改配置文件内容（以下只是示例；不要输入注释）:

      ```python
      # 连接主机显示的名称host_name，自己命名
      Host host_name  
         # 服务器的IP地址, 用zerotier外网访问时为虚拟IP地址
         HostName 192.xx.xx.xx     
         # 用于登录远程服务器的用户名user_name
         User user_name              
         # 用于登录远程主机的端口号(管理员指定)
         Port 22      
         # 本地私钥文件id_rsa的路径
         IdentityFile "C:\Users\admin\.ssh\id_rsa"              
      ```

      多个连接（多台服务器）则按上述格式在config文件里继续加内容即可。

   4. 保存退出config文件，看到左侧边栏SSH下多出了刚才配置的主机名称（如没有则重启一下vscode）。

   5. 右键主机名，选择在当前窗口或新窗口进行连接；弹出菜单选linux，continue。看到左下角状态变为远程连接服务器状态（SSH：host_name）即成功连接。

   6. vscode打开之前上传到服务器的代码文件夹，即可操作、编辑服务器上的代码文件。

4. 远程代码运行

   1. 服务器端安装vscode扩展中的python插件，安装后，右下角提示select interpreter，点击后弹出窗口。注意选择自己创建并配置好的conda环境。而后即可正常运行.py文件。

   2. 选中插件侧边栏，可以看到此时插件栏分为 “local” 和 “SSH:host_name” 两部分。所有涉及代码运行的本地插件都需要在服务器端再安装一次（python，jupyter等）。其他本地配过的插件，依据功能按需在服务器端装。

   3. 如要运行.ipynb文件（jupyter_notebook文件），则需在服务器端装jupyter插件。扩展栏搜索jupyter，安装在服务器端即可。运行.ipynb文件中的cell时，vscode会提示再次选择python interpreter（同上，选自己的conda环境），而后可能弹窗提示当前环境下无ipykernel（IPython kernel），并提供安装选项，点安装即可。自动安装好后，.ipynb文件中的每一个cell即可正常运行。