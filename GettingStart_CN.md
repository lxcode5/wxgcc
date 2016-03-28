wxgcc是一个开源的C/C++编辑软件，该软件轻型小巧，支持代码高亮，支持即时输入即时运行；是对著名的GCC开源编译工具的简单图形前端实现，通过wxpython语言开发而成。支持Windows XP，Windows 7 和 Linux 等多个平台。

wxgcc适用对象：
  * C/C++初学者
  * 不习惯终端操作的Linux用户
  * 不喜欢Windows下庞大编译环境的Windows用户
  * 阅读代码时需要随时验证某一个C/C++语言特性的用户

在运行wxgcc程序之前，请先确认在你的系统中是否已经安装了Python, wxPython以及GCC编译环境。

### 对于Ubuntu/Linux用户 ###
> 可以通过如下命令安装wxPython:
```
    $ sudo aptitude install python-wxgtk2.8 libwxgtk2.8-dev python-wxtools libwxbase2.8-0 libwxgtk2.8-0 python-wxglade
```

> 对于Linux系统，VTE虚拟终端库也是需要安装的，不过Linux系统应该都已经默认安装了，因为Gnome-Terminal程序也是依赖该库的。

> 如果不是很确定，可以通过如下命令安装：
```
    $ sudo aptitude install libvte-common libvte-dev libvte9 python-vte
```

> 其它Linux发行版可通过自己的包管理工具（如yum, emerge等）进行安装。

> 至于GCC则一般都会被默认安装到各个Linux发行版之中。

> 进入到wxgcc目录后可通过如下命令启动该程序：
```
    $ python wxgcc.py &
```

### 对于Windows用户(注意从v1.8.5开始才支持Windows) ###
> a) 下载安装mingw-get-inst-20110316.exe： http://sourceforge.net/projects/mingw/files/Automated%20MinGW%20Installer/mingw-get-inst/mingw-get-inst-20110316/

> 注意：
    * 有些杀毒软件（如诺顿）会自动删除上面下载的mingw可执行文件，所以你可能需要先关闭杀毒工具，然后再下载安装。
    * 安装过程进入到"Select Components"画面时，需要选中C++模块。
    * 安装过程中需要下载一些软件包，所以请确保网络畅通。
    * 其它安装选项默认即可。

> 安装结束后，需要将路径“C:\MinGW\bin”添加到PATH环境变量之中（"我的电脑"属性->高级->环境变量->系统变量->PATH的最后添加：";C:\MinGW\bin"，注意前面的分号）；然后就可以“运行->CMD”，输入"gcc -v"或者"g++ -v"就能看到gcc/g++的版本信息了。

> b) 下载安装python-2.7.msi：http://www.python.org/ftp/python/2.7/

> c) 下载安装wxPython2.8-win32-unicode-py27： http://www.wxpython.org/download.php （注意：安装的最后一个画面有一个“将.py编译成.pyc”的选项需要选中，然后确定结束安装）

> d) 下载安装py2exe-0.6.9.win32-py2.7.exe： http://sourceforge.net/projects/py2exe/files/py2exe/0.6.9/

> 使用默认选项安装b), c), d)即可，安装结束后同样需要将路径"C:\Python27"添加到PATH环境变量之中

> 然后就可以通过双击wxgcc.py文件启动该程序了。

（如果出现启动失败的情况，可以通过cmd终端先cd到wxgcc\_v1.8.6目录，然后执行“python wxgcc.py”进行启动，然后终端会显示错误的信息；可能会存在两个原因：一是"import wx"失败，需重装(c)步骤；二是找不到GtkWin类，可以通过记事本打开wxgcc.py,然后将倒数第二行注释掉即可，通过#号注释，改成这样：#gwin = GtkWin()，然后保存再次双击应该就能启动了。）

使用技巧：
  * 多使用tab键进行代码对齐操作(每个Tab被转换成8个Space)
  * 使用Backspace删除多个空格(每次会删除8个Space, 相当于一个Tab)
  * 语法高亮的变更只有在Space或Enter键弹起（ON\_KEY\_UP）时触发

常用快捷键：
  * F5 --- 编译并执行
  * F11 --- 全屏显示
  * Ctrl + L --- 锁屏进入只读状态
  * Ctrl + F/R --- 查找/替换
  * 其它的见程序的菜单栏

有关于wxgcc的任何疑问请发Email至：zwang@ucrobotics.com<br>
关于wxgcc的更多信息请访问：<a href='http://www.ucrobotics.com/index.php/zh/forum/7-Wxgcc%E5%BC%80%E6%BA%90%E9%A1%B9%E7%9B%AE'>http://www.ucrobotics.com/index.php/zh/forum/7-Wxgcc%E5%BC%80%E6%BA%90%E9%A1%B9%E7%9B%AE</a>