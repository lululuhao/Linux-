![http://www.magedu.com/](http://www.magedu.com/wp-content/uploads/2017/09/logo.png)

# 计算机基础--服务器
## 服务器的分类  
服务器按应用功能可分为：

&ensp;&ensp;&ensp;&ensp;Web服务器、数据库服务器、文件服务器、中间件应用服务器、日志服务器、监控服务器，程序版本控制服务器、虚拟机服务器、邮件服务器、打印服务器、域控制服务器、多媒体服务器、通讯服务器、ERP服务器等。
服务器按外形分类：
塔式服务器、刀片式服务器、机架式服务器。
## 服务器的尺寸
&ensp;&ensp;&ensp;&ensp;服务器宽度标准为19英寸（48.26cm），
高度（厚度）为1U=1.75英寸=44.45毫米
服务器一般有1U,2U,4U...
深度为600mm，800mm，900mm，1000mm
服务器机柜通常为42U约两米高。
**放服务器机柜一般用600mm,深1000mm，高2000mm；**
放网络设备机柜一般用深度为800mm。
## 服务器常用CPU
>Intel   

    Xeon 志强  
    Itanium 安腾  
 >AMD  

     ALthion 

>IBM  

    power  
### CPU频率  
 主频： 

 &ensp;&ensp;&ensp;&ensp;主频是CPU的时钟频率(CPU Clock Speed)，是CPU运算时的工作的频率（1秒内发生的同步脉冲数）的简称。单位是Hz。

 外频：

 &ensp;&ensp;&ensp;&ensp;系统总线的工作频率， CPU与外部（主板芯片组）交换数据、指令的工作时钟频率。 

 倍频： 

 &ensp;&ensp;&ensp;&ensp;倍频则是指CPU外频与主频相差的倍数。  
 三者关系是：**主频=外频x倍频**  
 常见的热插拔设备：硬盘，电源，PCI设备，风扇等  
 裸漏在机箱外的设备一般都支持热插拔。
### 服务器内存  
&ensp;&ensp;&ensp;&ensp;内存带宽是内存与北桥芯片之间的数据传输率,内存断电后数据丢失。外存断电后数据可以保存 。   
内存带宽=内存总线频率X数据总线位数/8  
1Byte（字节）=8bit（位）  
100Mbps  1G bit s  
100Mbps带宽=12.8MB/s 下载速度   
**1B=8b  Byte  bit**
### 硬盘
硬盘接口类型：

>IDE接口：硬盘接口规范，采用ATA技术规范  
SCSI接口：应用于小型机上的高速数据传输技术 
SATA接口： Serial ATA，提高传输速率，支持热插拔 
SAS接口： Serial Attached SCSI，兼容SATA  

目前主流的硬盘接口为SATA和SAS接口 
# 存储基础知识--存储网络    
DAS-----直接连接存储(Direct Attached Storage)  
数据块     磁盘和服务器可以分离，易于管理，但数据较为分散，连接距离短

NAS-----网络连接存储(Network Attached Storage)  
文件    不占用应用服务器资源，即插即用，用于文件服务器，不适合存储量大的设备

SAN-----存储区域网络(Storage Area Networks)  
数据块   高扩展性，数据集中易于管理，贵且安装和升级复杂    
# 操作系统
OS分类：  

服务器OS：RHEL, CentOS,Windows Server,AIX  

桌面OS：Windows 10,Windows 7,Mac OS，Fedora 

移动设备OS：Andriod,IOS,YunOS  

## 开发接口标准   
ABI接口：应用程序与OS之间的底层接口，允许编译好的目标代码在使用兼容ABI的系统中无需改动就能运行 

API接口：API定义了源代码和库之间的接口，因此同样的源代码可以在支持这个API的任何系统中编译  
# Linux哲学思想  
>一切都是一个文件（包括硬件）  
>小型，单一用途的程序   
>链接程序，共同完成复杂的任务  
避免令人困惑的用户界面  
配置数据存储在文本中  
# 终端terminal  
### 设备终端  
键盘鼠标显示器  
### 物理终端（/dev/console ）  
控制台console  
### 虚拟终端  
(tty：teletypewriters，/dev/tty# #为[1-6])
tty可有n个，Ctrl+Alt+F[1-6]  
### 图形终端  
/dev/tty7 ）startx, xwindows  
CentOS 6: Ctrl + Alt + F7
CentOS 7: 在哪个终端启动，即位于哪个虚拟终端
### 串行终端  
（/dev/ttyS# ）
ttyS  
### 伪终端  
（pty：pseudo-tty，/dev/pts/# ）
pty, SSH远程连接  
### 查看当前的终端设备：  
tty  
# 交互式接口  
交互式接口：启动终端后，在终端设备附加一个交互式应用程序  
GUI：Graphic User Interface   

X protocol, window manager, desktop  
Desktop:
GNOME (C, 图形库gtk)，  
KDE (C++,图形库qt)  
XFCE (轻量级桌面)  

CLI：Command Line Interface 

shell程序：sh(bourn 史蒂夫·伯恩)cshtcshksh(korn)bash (bourn again shell)GPL zsh  
# 命令提示符
命令提示符：prompt  
[root@localhost~]#  
#管理员  
$ 普通用户  
显示提示符格式  
[root@localhost~]#echo $PS1  
修改提示符格式  
**PS1**="\[\e[1;5;41;33m\][\u@\h \W]\\$\[\e[0m\]"  
>\e \033      ......               \u 当前用户  
\h 主机名简称      ......     \H 主机名  
\w 当前工作目录    ......    \W 当前工作目录基名  
\t 24小时时间格式   ......    \T 12小时时间格式  
\! 命令历史数     ......     \# 开机后命令历史数 
# 常见命令及使用  
## 内部命令

内部命令：由shell自带的，而且通过某命令形式提供

>help或者enable查询全部内部命令  
type+命令 查询命令是否为内部命令，是则显示builtin，不是则显示路径  
enable -n cmd禁用内部命令  
enable -n+命令 禁用命令   
enable -n 查询被禁用的命令  内部命令执行速度快  
优先找内部命令，如果没有再去外部找外部命令
## 外部命令  
外部命令：在文件系统路径下有对应的可执行程序文件
查看路径：
>which -a |--skip-alias; whereis  
which+命令查询命令路径  
whereis+命令 查询命令路径及其配置文件，更详细  

# 执行外部命令  
### Hash缓存表  
&ensp;&ensp;&ensp;&ensp;系统初始hash表为空，当外部命令执行时，默认会从PATH路径下寻找该命令，找到后会将这条命令的路径记录到hash表中，当再次使用该命令时，shell解释器首先会查看hash表，存在将执行之，如果不存在，将会去PATH路径下寻找。利用hash缓存表可大大提高命令的调用速率  
长命令 
### **hash**常见用法  
* hash 显示hash缓存  
* hash –l 显示hash缓存，可作为输入使用  
* hash –p path name 将命令全路径path起别名为name  
* hash –t name 打印缓存中name的路径  
* hash –d name 清除name缓存  
* hash –r 清除缓存  

# 命令别名
&ensp;&ensp;&ensp;&ensp;alias +自定义名字=一长串命令，输入自定义名字可以代替在命令行中定义的别名，仅对当前shell进程有效，如果想永久有效，要定义在配置文件中：  
仅对当前用户：~/.bashrc  
对所有用户有效：/etc/bashrc  
unalias+自定义命令  取消这个别名  
### 命令格式
>-n  短选项  例如：-l, -h  
--n长选项  例如：--all, --human-readable  
-e加\ 解释功能  

# 日期和时间  
Linux的两种时钟  
系统时钟：由Linux内核通过CPU的工作频率进行的
硬件时钟：主板
相关命令  
>date 显示和设置系统时间  
date +%s   
date -d @1509536033  
hwclock，clock: 显示硬件时钟  
-s, --hctosys以硬件时钟为准，校正系统时钟  
-w, --systohc以系统时钟为准，校正硬件时钟  
时区：/etc/localtime  
显示日历：cal–y  

# 简单命令
* 关机：halt, poweroff   
* 重启：reboot  
* -f: 强制，不调用shutdown  
* -p: 切断电源  
* 关机或重启：shutdown  
* shutdown [OPTION]... [TIME] [MESSAGE]  
* -r: reboot  
* -h: halt  
* -c：cancel  
* TIME：无指定，默认相当于+1（CentOS7）  
* now: 立刻,相当于+0  
* +m: 相对时间表示法，几分钟之后；例如+3  
* hh:mm: 绝对时间表示，指明具体时间  
* 例如：shutdown +5 -h  5分钟后关机  
* shutdown +5 -r  5分钟后重启  
* shutdown  -c  取消关机  
* 用户登录信息查看命令：
* whoami: 显示当前登录有效用户
* who: 系统当前所有的登录会话
* w: 系统当前所有的登录会话及所做的操作
## **screen命令** （重点）  
>创建新screen会话  
screen –S [SESSION]  
加入screen会话  
screen –x [SESSION]  
退出并关闭screen会话  
exit  
剥离当前screen会话  
Ctrl+a+d  
显示所有已经打开的screen会话  
screen -ls  
恢复某screen会话  
screen -r [SESSION]

例如：
* screen -S help  创建一个名为help的会话  
* screen -ls 查看其他人创建的会话  
* screen -x help  加入名为help的会话，两个终端可以同步操作  
* screen 可以单独开一个终端，在开的临时会话中做任务，即使此时网络或者系统出现问题，也不会丢失任务  

## echo命令  

功能：显示字符  
语法：echo [-neE][字符串]  
说明：echo会将输入的字符串送往标准输出。输出的字符串间以空白字符隔开, 并在最后加上换行号  
选项：  
>-E （默认）不支持\解释功能  
-n 不自动换行  
-e 启用\字符的解释功能  

显示变量  
echo "$VAR_NAME” 变量会替换，弱引用  
echo '$VAR_NAME’  变量不会替换，强引用   
例如：  
 >echo  {1,2,3}  
1 2 3   
echo 1 2 3   
1 2 3  
echo file {1,2,3}  
file1 file2 file3  
echo file {1,2,3}  
echo file {1,2,3}.{txt}  
file1.txt file2.txt file3.txt  
echo file {1,2,3}.{txt,log}  
file1.txt file1.log file2.txt file2.log   file3.txt file3.log  

启用命令选项-e 若字符串中出现以下字符，则特别加以处理，而不会将它当成一般文字输出 
* \a 发出警告声  
* \b 退格键  
* \c 最后不加上换行符号  
* \n 换行且光标移至行首  
* \r 回车，即光标移至行首，但不换行  
* \t 插入tab  
* \\插入\字符  
* \0nnn 插入nnn（八进制）所代表的ASCII字符  
* echo -e '\033[43;31;5mmagedu\033[0m'  
* \xHH插入HH（十六进制）所代表的ASCII数字（man 7 ascii）  
# 命令行历史  
&ensp;&ensp;&ensp;&ensp;保存你输入的命令历史。可以用它来重复执行命令，在登录shell时，会读取命令历史文件中记录下的命令~/.bash_history，登录进shell后新执行的命令只会记录在缓存中；这些命令会用户退出时“追加”至命令历史文件中，重复前一个命令，有4种方法：  
>1. 重复前一个命令使用上方向键，并回车执行  
>2. 按!! 并回车执行  
>3. 输入!-1 并回车执行  
>4. 按Ctrl+p并回车执行  

* !:0 执行前一条命令（去除参数）  
* Ctrl + n 显示当前历史中的下一条命令，但不执行  
* Ctrl + j 执行当前命令  
* !n 执行history命令输出对应序号n的命令  
* !-n 执行history历史中倒数第n个命令  
* !string 重复前一个以“string”开头的命令  
* !?string 重复前一个包含string的命令  
* !string:p仅打印命令历史，而不执行  
* !$:p 打印输出!$ （上一条命令的最后一个参数）的内容  
* !*:p打印输出!*（上一条命令的所有参数）的内容  
* ^string删除上一条命令中的第一个string  
* ^string1^string2将上一条命令中的第一个string1替换为string2  
* !:gs/string1/string2将上一条命令中所有的string1都替换为string2  

>使用up（向上）和down（向下）键来上下浏览从前输入的命令  
ctrl-r来在命令历史中搜索命令  
（reverse-i-search）`’：  
Ctrl+g：从历史搜索模式退出  
要重新调用前一个命令中最后一个参数  
!$ 表示   
Esc, .（点击Esc键后松开，然后点击. 键）  
Alt+ .（按住Alt键的同时点击. 键）  

* command !^ 利用上一个命令的第一个参数做cmd的参数  
* command !$ 利用上一个命令的最后一个参数做cmd的参数  
* command !n:* 调用第n条命令的所有参数  
* command !string:^ 从命令历史中搜索以string 开头的命令，并获取它的第一个参数  
* command !string:$ 从命令历史中搜索以string 开头的命令,并获取它的最后一个参数  
* command !string:n 从命令历史中搜索以string 开头的命令，并获取它的第n个参数  
* command !string:* 从命令历史中搜索以string 开头的命令，并获取它的所有参数  

# 命令history  
* HISTSIZE：命令历史记录的条数  
* HISTFILE：指定历史文件，默认为~/.bash_history  
* HISTFILESIZE：命令历史文件记录历史的条数  
* HISTTIMEFORMAT=“%F %T “ 显示时间  
* HISTIGNORE=“str1:str2*:… “ 忽略str1命令，str2开头的历史  

控制命令历史的记录方式：  
环境变量：HISTCONTROL  
>ignoredups默认，忽略重复的命令，连续且相同为“重复”  
ignorespace忽略所有以空白开头的命令  
ignoreboth相当于ignoredups, ignorespace的组合  

erasedups删除重复命令  
export 变量名="值“  
存放在/etc/profile 或~/.bash_profile  
# bash的快捷键(重点)  
* **Ctrl + l清屏，相当于clear命令**  
* Ctrl + o执行当前命令，并重新显示本命令  
* Ctrl + s阻止屏幕输出，锁定  
* Ctrl + q允许屏幕输出  
* Ctrl + c终止命令  
* Ctrl + z挂起命令  
* **Ctrl + a光标移到命令行首，相当于Home**  
* **Ctrl + e光标移到命令行尾，相当于End**  
* Ctrl + f光标向右移动一个字符  
* Ctrl + b光标向左移动一个字符  
* Alt + f光标向右移动一个单词尾  
* Alt + b光标向左移动一个单词首  
* Ctrl + xx光标在命令行首和光标之间移动  
* Ctrl + u从光标处删除至命令行首  
* Ctrl + k从光标处删除至命令行尾  
* **Alt + r 删除当前整行**  
* Ctrl + w从光标处向左删除至单词首  
* Alt + d从光标处向右删除至单词尾  
* Ctrl + d删除光标处的一个字符  
* Ctrl + h删除光标前的一个字符  
* Ctrl + y将删除的字符粘贴至光标后  
* Alt + c从光标处开始向右更改为首字母大写的单词  
* Alt + u从光标处开始，将右边一个单词更改为大写  
* **Alt + l从光标处开始，将右边一个单词更改为小写**  
* Ctrl + t交换光标处和之前的字符位置  
* Alt + t交换光标处和之前的单词位置  
* Alt + N提示输入指定字符后，重复显示该字符N次 

注意：Alt组合快捷键经常和其它软件冲突  

### whatis
whatis +命令  查询命令功能      
鼠标左键选择命令，右键可以直接粘贴该命令      
makewhatis安装whatis数据库   8.163.128 在伪终端直接输入用户名和密码登录终端  

# 好玩的欢迎界面！
nano /etc/motd    将下面图案写入motd，按ctrl+x，然后按enter保存，形成开机欢迎界面  

------------------  
                              _.._        ,------------.
                           ,'      `.    ( I want you! )
                          /  __) __` \    `-,----------'
                         (  (`-`(-')  ) _.-'
                         /)  \  = /  (  
                        /'    |--' .  \  
                       (  ,---|  `-.)__`  
                        )(  `-.,--'   _`-.  
                       '/,'          (  Uu",
                        (_       ,    `/,-' )
                        `.__,  : `-'/  /`--'
                          |     `--'  |
                          `   `-._   /
                           \        (
                           /\ .      \.  
                          / |` \     ,-\
                         /  \| .)   /   \
                        ( ,'|\    ,'     :
                        | \,`.`--"/      }
                        `,'    \  |,'    /
                       / "-._   `-/      |
                       "-.   "-.,'|     ;
                      /        _/["---'""]
                     :        /  |"-     '
                     '           |      /
                                 `      |

  