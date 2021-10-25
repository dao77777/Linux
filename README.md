> **作者:** dao77777
>
> **创建日期:** 2021/10/8
>
> **更新日期:** 2021/10/8

# 书
- [鸟哥私房菜](http://linux.vbird.org/)
- UNIX环境高级编程
- UNIX网络编程

# Linux发展史
- UNIX
  - BSD
  - System V
  - Minix
  - Linux
    - RHEL Fedora CentOS SuSE OpenSuSE: 使用RPM管理软件的Linux发行版
    - Ubuntu Debian B2D: 使用DPKG管理软件的Linux发行版
    - Android
    - 标准: POSIX, FHS, LSB
- GNU
  - Emacs
  - GNU C(GCC)
  - GNU C Library(glibc)
  - Bash shell
- Open Source
  - Apache License 2.0
  - BSD 3-Clause "New" or "Revised" license
  - BSD 2-Clause "Simplified" or "FreeBSD" license
  - GNU General Public License(GPL)
  - GNU Library or "Lesser" General Public License(LGPL)
  - MIT license
  - Mozilla Public License 2.0
  - Common Development and Distribution License
                
# 硬件
- CPU
  - CPU的组成: ALU CU X MAR MDR IR PC
  - 指令集
    - RISC: SPARC, PowerPC, ARM
    - CISC: x86
  - 性能指标: 主频
  - 超线程(Hyper-Threading HT): 4核8线程, 8核16线程, 线程数可以超过核心数
  - CPU性能测试软件: CPU-Z
- 主存
  - RAM
    - DRAM(随机存储器)
      - SDRAM, DDR
    - SRAM(高速缓存)
    - ROM(只读存储器)
      - EEPROM
- I/O设备
  - 辅存
    - HDD(机械硬盘), SSD(固态硬盘)
    - 硬盘概念: 磁区, 磁轨, 磁柱
    - 性能指标: IOPS
    - 文件系统
      - Linux: ext2/ext3/ext4, xfs, swap, bios boot 
      - Windows: ntfs
      - 网络: nfs, smbfs
      - 通用: fat, vfat
    - MSDOS, GPT
  - 显卡
  - I/O地址, IRQ中断
- 总线
  - 传输单位: 位, 字节, 字长
  - CPU与主存的数据传输解决方案
    - Intel
      - QPI, DMI
    - AMD
      - Hyper Transport
  - 片内总线
  - 系统总线
    - 前端总线(FSB): 集中在北桥芯片(高速设备通过北桥芯片连接CPU), 现继承在CPU中
    - 后端总线: 集中在南桥芯片(低俗设备的通过南桥芯片连接CPU)
- 接口
  - 串口， 并口
  - 通用: USB, 雷电, SCSI, PS/2
  - 显卡: PCI, AGP, PCI-E
  - 显示器: D-Sub, DVI, HDMI, Display port
  - 网口: RJ-45
  - 硬盘: SATA, SAS, IDE, M.2
- BIOS
  - CMOS

# 操作系统
## 层次
硬件->内核->系统调用->应用程序
## 文件管理
- /usr/share/doc: Linux文档
- 硬盘
  - /dev/sd[a-p][1-9]?: SCSI/SATA/USB, 其中1-4为主要分割槽, 5-9为逻辑分割槽
  - /dev/vd[a-p]: 虚拟机
  - /dev/fd[0-1]: 软盘
  - /dev/hd[a-d]: IDE硬盘(旧式系统才有)
- 打印机
  - /dev/usb/lp[0-15]: USB接口打印机
  - /dev/lp[0-15]: 打印机
- 鼠标
  - /dev/input/mouse[0-15]: 鼠标
  - /dev/psaux: PS/2接口的鼠标
  - /dev/mouse: 当前鼠标
- CDROM/DVDROM
  - /dev/scd[0-1]
  - /dev/sr[0-1]
  - /dev/cdrom 
- 磁带
  - /dev/ht0
  - /dev/st0
  - /dev/tape
## 权限管理
## 软件管理
- tarball
- rpm
- dpkg
- yum
- apt
## 文本编辑
- vi
## Shell
- cmd
  - other
    - uuidgen: 生成uuid
  - 机器
    - /etc/os-release: linux发行版详细信息
    - /proc/cpuinfo: cpu的详细信息
    - uname -r: 查看linux内核版本
    - /etc/hostname: 主机名
    - locale: 查看语系
      - LANG = <语系>, export LC_ALL=<语系>: 改变语系, zh_CN.UTF-8代表中文, en_US.utf8代表英文
    - date, cal: 查询时间及日历
    - bc: 计算器
    - --help, man, info, /usr/share/doc: 文档
    - sync: 主存数据同步到辅存
    - init <runLevel>: 常用运行级别未3, 5
      - 0: 关机
      - 1: 单用户
        1. 重启过程中按e进入编辑界面
        2. 找到fi linux16
        3. 在UTF-8后空格添加init=/bin/sh
        4. 摁ctrl+x进入单用户模式
        5. 输入mount -o remount, rw /
        6. 在新的一行输入passwd, 然后输入两次密码
        7. 输入touch /.autorelabel
        8. 输入exec /sbin/init
      - 2: 多用户状态无网络服务
      - 3: 多用户状态有网络服务
      - 4: 系统未使用保留给用户
      - 5: 图形界面
      - 6: 重启
    - systemctl get-default: 获取默认运行级别
    - systemctl set-default <runLevel>: 设置默认运行级别, multi-user.target表示运行级别3, graphical.target表示运行级别5
    - shutdown
      - -h now: 立即关机
      - -h <number>: 指定分钟关机
      - -r now: 立即重启
      - -r <number>: 指定分钟后重启
    - halt: 关机
    - reboot: 重启
  - 文件
    - 目录树
      - pwd: 打印当前工作目录
        - -P: 真实路径, 而不是链接
      - ls
      - basename <path>: 给出路径文件名
      - dirname <path>: 给出路径目录名
      - file <filename>: 查看文件类型, 有没有使用到动态函数库等信息
      - which <cmd>: 查询命令所在路径
      - whereis
      - locate
      - find <finame | dirname>: 从指定目录开搜
        - -name <filename | dirname>: 指定文件或目录
        - -user <user>: 指定用户
        - -size <file_size>: 指定文件大小(+n 大于, -n小于, n等于, 单位k, M, G)
        - -atime <day>: 指定天数(+n大于, -n小于, n等于)
      - cd <dirname>: 切换目录
      - mkdir <dirname>: 创建目录
        - -p: 创建多级目录
      - touch <filename>: 创建文件
      - cp <source> <dest>: 复制
      - ln
      - mv <source> <dest>: 剪切(重命名)
      - rm -rf <filename | dirname>: 删除
      - ln <source> <dest> [-r]: 创建链接/软链接
    - 内容
      - od <filename>: 二进制的方式读取文档
        - -t: 设置显示类型
          - a       : 利用預設的字元來輸出；
          - c       : 使用 ASCII 字元來輸出
          - d[size] : 利用十進位(decimal)來輸出資料，每個整數佔用 size bytes
          - f[size] : 利用浮點數值(floating)來輸出資料，每個數佔用 size bytes
          - o[size] : 利用八進位(octal)來輸出資料，每個整數佔用 size bytes
          - x[size] : 利用十六進位(hexadecimal)來輸出資料，每個整數佔用 size bytes
      - cat <filename>
      - more <filename>
      - less <filename>
      - head <filename>: 显示头几行
        - -n <行数>: 指定行数
      - tail <filename>: 显示末几行
        - -n <行数>: 指定行数
        - -f: 同步刷新
      - vi | vim | nano <filename>: 文本编辑
      - grep
      - awk
      - sed
      - wc
      - cut
      - sort
      - uniq
      - |: 管道符
      - >: 输出重定向, 覆盖
      - >>: 输出重定向, 追加
    - 硬盘
      - df [<path>]: 硬盘使用情况, df -hT
        - -h: 以易读的方式显示
        - -a: 列出所有文件系统
        - -T: 显示文件系统类型(如ext2/3/4, xfs等)
      - du [<path>]: 文件占用磁盘情况
        - -a: 列出所有文件
        - -h: 以易读的方式显示
        - -s: 只列出总容量
      - lsblk: 列出所有磁盘
        - -f: 列出磁盘的UUID
      - parted: 磁盘分割
      - fdisk: MBR分割表使用的磁盘分割工具
      - gdisk: GPT分割表使用的磁盘分割工具
      - mkfs.<file_system> <device>: 格式化分区的文件系统
        - -f: 强制格式化, 可以用来格式化一些文件用来mount -o loop挂载
      - mount UUID="<UUID>"/<device> <path>: 挂载分区
        - -o <params>: 设定各种挂载参数, -o loop 可用来挂载iso映像文件
      - umount <device>/<mount point>: 卸载分区
      - mkswap <device>: 格式化分区文件系统为swap格式
      - swapon <device>: 开启该swap分区
        - -s: 查看swap分区的使用情况
      - free: 查看内存与swap分区的占用情况
        - -h: 以易读的方式显示
      - /etc/fstab: 开机挂载设置, 格式为 UUID 挂载点 文件系统 参数 dump fsck
    - 压缩备份
      - tar
        - -z: gzip压缩/解压
        - -j: bzip2压缩/解压
        - -J: xz压缩、解压
        - -c: 打包 
        - -x: 解包
        - -t: 查询
        - -v: 过程中显示文件名
        - -f <filename>: 指定目标文件
        - -C <path>: 用于在解压缩中指定目录
        - -p: 保留文件权限与属性
        - -P: 保留绝对路径
        - --exclude=<filename>: 排除某个文件
      - xfsdump
      - xfsrestore
      - mkisofs
      - isoinfo
      - cdrecord
      - cpio
      - dd if=<input_file> of=<output_file> bs=<block_size> count=<block_count>
  - 权限
    - /etc/passwd: 用户配置文件, 每行含义 用户名:口令:uid:gid:注释/主目录/登录shell
    - /etc/shadow: 加密后的用户口令
    - /etc/group: 组配置文件, 每行含义 组名:口令:gid:组内用户列表
    - visudo: 修改sudo用户
    - umask <right>: 新创建文件或目录时默认去掉的权限, 文件默认rw-rw-rw-, 目录默认rwxrwxrwx, 减去umask的right得到默认权限
    - useradd <username>: 添加用户
    - userdel <username>: 删除用户
    - usermod <username>: 修改用户
      - -g <groupName>: 修改用户组名
      - -d <path>: 修改homedir路径
    - passwd <username>: 修改用户口令
    - id <username>: 查询用户信息
    - who: 查询当前用户
    - su <username>: 切换当前用户
    - groupadd <groupName>: 添加组
    - groupdel <groupName>: 删除组
    - chown <username> <path>: 改变资源所属用户
    - chgrp <groupName> <path>: 改变资源所属组
    - chmod <right> <path>: 改变资源权限, right中 r=4 w=2 x=1, 如chmod 751 ./wow.md
  - 软件管理
    - rpm
      - -q <packageName>: 查询是否安装指定软件包
      - -qa: 查询所有已安装软件包
      - -qi <packageName>: 查询已安装指定软件包信息
      - -ql <packageName>: 查询已安装指定软件包中的文件
      - -qf <path>: 查询dir或file属于哪个软件包
      - -e[ --nodeps] <packageName>: 卸载[强制]指定软件包
      - -ivh <path>: 安装指定软件包
    - yum
      - /etc/yum.repos.d: 配置文件
      - yum install 包: 安装指定包
      - yum remove 包: 卸载指定包
      - yum search 包: 搜索包的相关信息
      - yum provides 包: 查看包来源
      - yum whatprovides 命令: 查询命令在什么包中
      - yum list: 查看服务器中可安装的软件包列表
      - yum info kernel -q: 检测内核版本, 显示可以升级的内核
      - yum-config-manager --add-repo 仓库: 更新仓库
      - yum makecache fast: 更新源
      - yum update kernel: 升级内核
    - dpkg
      - -l: 显示已安装的软件列表
      - -i 包: 安装指定包
      - -i --instdir=包安装路径 包: 安装包到制定路径
      - -r 包: 删除指定包
      - -P 软件: 删除软件同时删除其配置文件
      - -L 软件: 显示与软件关联的文件
      - --unpack: 解开包
      - -c: 显示包内文件列表
      - --configure: 配置软件
    - apt
      - /etc/apt/sources.list: 修改源
      - apt-get update: 更新源
      - apt-get dist-upgrade: 更新系统
      - apt-get install 包名: 安装包
        - --reinstall: 重新安装
        - -f: 修复安装
      - apt-get build-dep 包名: 安装相关的编译环境
      - apt-get source 包名: 下载包的源码
      - apt-get upgrade: 更新已安装的包
      - apt-get remove 包名: 卸载包
        - --purge: 删除包括配置文件
      - apt-cache search 包名: 搜索包
      - apt-cache show 包名: 获取包信息
      - apt-cache depends 包名: 获取包的依赖信息
      - apt-cache rdepends 包名: 获取包的被依赖信息
  - 进程
    - ps -aux|-ef: 查看进程状态
    - top: 动态监控进程状态
    - kill <PID>: 终止进程
      - -9: 强制终止
  - 网络
    - /etc/sysconfig/network-scripts/网卡: 配置文件
    - netstat -ano|-tln: 查询网络状态
    - ping <IP>: 测试主机是否能ping通
    - telnet <IP> <PORT>: 测试指定IP与PORT的服务
    - curl <IP> <PORT>: 发送HTTP请求
      - -I: 显示头部
      - -d <param>: 携带参数
      - -X <method>: 指定请求方法
      - -H <head>: 自定义头部
    - wget <URL>: 下载文件
    - export http_proxy="http:<IP>:<PORT>": 设置http代理
  - 服务
    - 配置文件
      - /usr/lib/systemd/system目录: systemctl可以管理的服务
      - /etc/init.d目录: service指令管理的服务
    - systemctl start或stop或restart或reload或status 服务名: 启动指定服务
    - setup: 查看服务, 设置服务自启动
    - chkconfig 服务名 off或on: 查看service管理的服务在各个运行级别下的自启动状态
      - --list: 查看服务
      - --level 运行级别 服务名 off或on: 设置服务在各个级别上的自启动
    - systemctl list-unit-files: 查看systemctl管理的服务在3和5运行级别下的自启动状态
    - systemctl enable 服务名: 设置服务在3和5运行级别下自启动
    - systemctl disable 服务名: 关闭服务在3和5运行级别下自启动
    - systemctl is-enabled 服务名: 查询指定服务是否在3和5运行级别下自启动
  - 防火墙
    - 客户: firewall-cmd
    - 服务: firewalld
    - 指令
      - firewall-cmd --list-all: 查看用户开放的所有端口
      - firewall-cmd --zone=public --list-ports: 查看所有用户自己开放的端口
      - firewall-cmd --permanent --add-port=端口号/协议: 开放端口访问
      - firewall-cmd --permanent --remove-port=端口号/协议: 关闭端口访问
      - firewall-cmd --reload: 重新载入服务才能生效
      - firewall-cmd --query-port=端口/协议: 查询端口是否开放
  - 任务调度
  - dd if=centos7.iso of=/dev/sdc: 烧录iso文件
- script
## 网络
## 虚拟化
- VirtualBox
- VMWare
- KVM(Linux自带)
- WSL
## SSH
- `ssh <username>@<host>`: ssh进行登录, 指定用户与主机
  - `-i <private_key_path>`: 以公私钥的方式认证, 指定私钥文件地址
  - `-p <port>`: 指定ssh连接的端口号, 默认22
- `ssh-keygen -o`: 生成公私钥匙, 默认生成地址为`~/.ssh`
- `scp`
- `~/.ssh/authorized_keys`: 配置认证的用户, 用公钥表示
- `~/.ssh/known_hosts`: 与另一用户进行ssh通信后会自动生成known_hosts, 表示知道了该用户
- `~/.ssh/config`: 用于配置ssh通信的目标, 本来是ssh `<username>@<host> -p <port> -i <private_key_path>`连接目标用户, 配置了后直接ssh config_user连接目标用户, 格式为
  ```
  Host <config_user>
    User <username>
    HostName <host>
    Port <port>
    IdentityFile <private_key_path>
  ```
- `~/.ssh/id_rsa`: 私钥文件, ssh-keygen生成的默认地址
- `~/.ssh/id_rsa.pub`: 公钥文件, ssh-keygen生成的默认地址





进程管理
内存管理
文件系统
I/O模型


NAT, SAMBA, MAIL, WEB, DHCP, FTP
RAID

- CMOS: DRAM, 记录主板参数, 系统时间,CPU电压与频率, 各项设备I/O地址与IRQ
- BIOS/UEFI: ROM, 引导程序

- 辅存
  - 分割类型
    - MBR
    - GPT
  - 磁轨, 磁柱, 磁区
  - 磁区大小
    - MBR硬盘: 512byte
    - GPT硬盘: 4K
  - 第一磁区
    - 开机启动文件: 446byte, 含开机启动管理程序, Linux中是grub
    - 分割表
      - MBR硬盘: 64byte, MSDOS格式
      - GPT硬盘: 4K - 446byte, GPT格式
  - 分区
    - 分类: 主分区/扩展分区/逻辑分区
    - 组成
      - boot sector: 开机启动块, 多系统的来源
      - 多个block group
        - super block
        - inode
        - block bitmap
        - inode bitmap
        - data block


- 文件种类
  - -: 常规文件
    - 纯文字
    - 二进制
    - 特定格式
  - d: 目录
  - l: 链接
  - b: 区块设备, 可以随机在设备不同区块中读写, 如硬盘
  - c: 字符设备, 一次性读取, 能够不断输出的设备, 如键鼠
  - s: 套接字
  - p: 管道

- 路径
  - .: 当前目录
  - ..: 上级目录
  - -: 上一个目录
  - ~: 家目录

CPU, 显卡, 主存, 辅存, 网卡, 总线, 其它设备
BIOS/UEFI, MBR开机管理程序, 操作系统
进程管理, 文件系统, 权限

- 环境变量
  - $PATH: 记录了所有
内存
- 文件
  - metadata: fileSystem description, superblock, inode bitmap, block bitmap
  - data: inode, data block
  - 索引式文件系统, 链式文件系统
  - mtime: 内容更新时间
  - ctime: 权限属性更新时间
  - atime: 内容被取用更新时间
权限
  - 普通权限
  - 隐藏权限
  - 特殊权限
    - SUID, SGID, SBIT
软件
进程
网络

- .Z: compress
- .zip: zip
- .gz: gzip
- .bz2: bzip2
- .xz: xz
- .tar: tar, 只进行打包, 不进行压缩
- .tar.gz: tar打包与gzip压缩
- .tar.bz2: tar打包与bzip2压缩
- .tar.xz: tar打包与xz压缩

- Bourne SHell(sh)
- C SHell
- K SHell
- TCSH
- Bourne Again SHell(bash)
- /etc/shells: 可以使用的shell
- ~/.bash_history: 上次登录的命令的历史记录
- type <cmd>: 查看该指令是否内建
- \可以跳脱回车键
- 环境变量
  - HOME: 家目录
  - SHELL: 当前环境用的哪个shell程序
  - HISTSIZE: 历史命令的个数
  - MAIL: 邮件
  - PATH: 路径
  - LANG: 语系
  - RANDOM: 随机数
- 自定变量
  - HISTFILE: 历史命令放置的文档
  - PS1: 命令提示符
  - PS2: 命令跳脱符
  - $: 当前shell使用的PID
  - ?: 刚执行完的指令的回传值
- ${<variable>}: 表示变量
  - <variable[#|##|%|%%]delete>: 表示该变量删除delete部分后的值, #从前删除最短的, ##从前删除最长的, %从后删除最短的, %%从后删除最长的
  - <variable[/old/new|//old/new]>: 替换变量中指定字符串, /表示替换一次, //表示替换所有
  - <variable[-|:-|=|?]default>: -表示若变量不存在用默认代替, :-表示若变量不存在或为空用默认代替, =表示在-基础上用默认值给variable赋值, ?表示不存在则报错
- $(<cmd>): 表示执行命令后返回的值
- <variable>="<value>": 设置变量的值
- unset <variable>: 取消变量设置
- export <variable>: 将变量变为环境变量
- echo ${<variable>}: 打印变量
- env: 查看环境变量
- set: 显示该shell所有变量
- read [-p <tips>] [-t <wait_time>] <variable>: 与键盘交互
- declare [-aixrp <variable>]: 设置变量的类型, a为数组, i为整型, x为环境变量(+x为取消环境变量), r为只读, p为显示该变量的属性
- ulimit [-SHacdfltu]: 设置使用者的限制
- alias <alias>=<cmd>: 给命令起别名, 不加参数则显示所有别名
- unalias <alias>: 取消别名设置

- ~/.bash_logout
- ~/.bashrc: 用户登录bash初始化指令
- locale -a: 显示所有支持的编码
- locale: 显示语系相关的变量
- /usr/lib/locale
- /etc/locale.conf
- /etc/issue, /etc/motd: 进站欢迎信息
  - \d 本地端時間的日期
  - \l 顯示第幾個終端機介面
  - \m 顯示硬體的等級 (i386/i486/i586/i686...)
  - \n 顯示主機的網路名稱
  - \O 顯示 domain name
  - \r 作業系統的版本 (相當於 uname -r)
  - \t 顯示本地端時間的時間
  - \S 作業系統的名稱
  - \v 作業系統的版本
- /etc/profile
- ~/.bash_profile
- ~/.bash_login
- ~/.profile

主机名
开机语
欢迎语
命令行提示符
命令行跳脱符
语系
环境变量
自定变量
文件
权限
进程
网络