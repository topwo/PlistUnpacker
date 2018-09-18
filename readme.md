##usage
	python plistUnpacker.py [Directory/xxx.plist]
	
##usage
	python pvr2png.py [source Path] [suffix] [OutPath:option]
	
	
大家先把文件下载下来，下面我介绍如何使用：

　　　这里我提供了两个工具pvr2png.py和plistUnpacker.py。pvr2png.py用于将pvr/pvr.ccz等Texturepacker的压缩格式转换成png；plistUnpacker.py用于将plist和png文件转换成散图。

一、如何将pvr/pvr.ccz图片转换成png（如果你的资源已经是png，可以跳过这步）

　　首先我们要装一个工具Texturepacker(这里我就不同下载链接了自己可以网上down)，然后选择安装Texturepacker命令行工具：

　　完成之后我们的准备工作已经完了，下面就可以直接转图了。

python pvr2png.py [source Path] [suffix] [OutPath:option]
　　[source Path]:为pvr/pvr.ccz的所在路径

　　[suffix]:为转换文件的扩展名(eg：pvr 、pvr.ccz...)

　　[OutPath]:为转换后的输出目录，可选。默认为当前目录

二、将plist和png文件转换成散图。

　　首先这里要安装两个python的工具 xml 和 PIL。安装的方法我就不做过多的赘述了。

　　下面就用的到了我的另一个脚本文件  plistUnpacker.py

python plistUnpacker.py [Directory/xxx.plist]
　　[Directory/xxx.plist]:输入的参数可以是一个目录或者是单个的plist文件

　　成功会在当前的目录下创建一个或多个与plist文件相同的文件夹并存放这些散图文件。
  
  http://www.cnblogs.com/relvin/p/5543612.html



Mac安装Pillow模块解决办法
2016.12.04 22:42 1936浏览  字号
Mac Python上安装Pillow报错：
ValueError: jpeg is required unless explicitly disabled using
问题原因：
这是因为在Pillow3.0以上的版本中libjpeg和zlib是必不可少的。安装这两个库后，Pillow便可正常安装。
http://stackoverflow.com/questions/34631806/fail-during-installation-of-pillow-python-module-in-linux
解决步骤：

打开终端窗口, 粘贴以下脚本。安装brew
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

通过brew安装libjpeg
brew install libjpeg zlib

通过brew安装zlib

brew tap homebrew/dupes
brew install zlib
brew link zlib --force
通过pip安装Pillow
sudo pip install Pillow
