# WinCC OA Chinese

#### 介绍
WinCC OA中文包

WinCC OA官方软件安装包有德文,英文,俄文三种语言包，不含中文包，为了让我们能够使用中文语言开发环境， 利用WinCC OA 自带的Translator的翻译工具实现字典的中文汉化。

#### 软件架构
软件架构说明

data/trans/dictionary.json
data/dplist/AES_Config.dpl
data/dplist/sys.dpl
msg/zh_CN.utf8/LogViewer.qm
msg/zh_CN.utf8/qt.qm
msg/zh_CN.utf8/uim.qm

AES_Config.dpl和sys.dpl,是GEDI环境下打开的系统管理界面的汉化.用到了一些内部DP点,多语言显示中文.
LogViewer.qm,qt.qm,uim.qm是LogViewer,GEDI,提示窗口等的软件内部多语言的汉化.
dictionary.json  --字典文件

#### 安装教程

step 1.  新建标准空项目.至少要选择"English-US(en_US.utf8), Simplfd.Chinese - China(zh_CN.utf8) "两种语言选项. Project Name可自己定义,比如"CN318";启动该项目.

step 2.  将内容解压到项目路径下

step 3.  运行菜单栏翻译工具:GEDI>Tools>Translator, 选择Import, 按下图进行配置:

![输入图片说明](https://www.winccoa.top/chinese/WinCC%20OA%20Chinese_files/image001.jpg)


其中Reference Languate : 选择English-US(en_US.utf8)

Language to import: 选择 Simplfd Chinese - China(zh_CN.utf8)

![输入图片说明](https://www.winccoa.top/chinese/WinCC%20OA%20Chinese_files/image002.jpg)

勾选Version Files 下的All单选项.

此时,应当可用在File:可看到"dictionary.json"的字典文件.

step 3.  点击Start按钮.等待数分钟自动完成全部的panel的汉化.

step 4. 报警/事件窗口表格汉化

在做这步骤之前，必须要打开一次：System Management > settings > A&E - Row/Screen > Edit Row，系统会在后台自动创建出_AESConfi DP类型下的_AESConfig ，_AESConfigRow这两个DP，再执行下面的汉化

  Gedi>System Management> Database> ASCII Manager

 Direction 选择Import

 导入AES_Config.dpl和sys.dpl文件,导入到系统,完成系统管理界面的汉化.
#### 使用说明

 验证一下汉化结果: 在Console 新建User Interface (option: -m gedi -lang zh_CN.utf8)

 目的:将翻译好的项目"CN318"作为一个库件来使用.我们只用到了翻译好的panels,msg,dplist三个文件里面的文件. 将项目从Console里注销,删除其他的不需要的文件夹的内容.

在自己的WinCC OA的项目的config文件里面,紧挨着pvss_path,新建一行,添加库文件路径
[general]
proj_path = "C:\WinCC_OA_Proj\CN318"

#### 主要贡献者

zhigang.li@live.cn