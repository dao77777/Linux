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
      - 通用: vfat
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
  - 机器
    - /etc/os-release: linux发行版详细信息
    - /proc/cpuinfo: cpu的详细信息
    - uname -r: 查看linux内核版本
    - /etc/hostname: 主机名
    - locale: 查看语系
      - LANG = <语系>, export LC_ALL=<语系>: 改变语系, zh_CN.UTF-8代表中文, en_US.utf8代表英文
    - date, cal: 查询时间及日历
    - bc: 计算器
    - /etc/profile: 环境变量配置文件
    - set: 查看环境变量
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
    - pwd
    - ls
    - find <finame | dirname>: 从指定目录开搜
      - -name <filename | dirname>: 指定文件或目录
      - -user <user>: 指定用户
      - -size <file_size>: 指定文件大小(+n 大于, -n小于, n等于, 单位k, M, G)
      - -atime <day>: 指定天数(+n大于, -n小于, n等于)
    - cat <filename>
    - more <filename>
    - less <filename>
    - head <filename>: 显示头几行
      - -n <行数>: 指定行数
    - tail <filename>: 显示末几行
      - -n <行数>: 指定行数
      - -f: 同步刷新
    - vi | vim <filename>: 文本编辑
    - cd <dirname>: 切换目录
    - mkdir <dirname>: 创建目录
    - touch <filename>: 创建文件
    - cp <source> <dest>: 复制
    - mv <source> <dest>: 剪切(重命名)
    - rm -rf <filename | dirname>: 删除
    - ln <source> <dest> [-r]: 创建链接/软链接
    - gzip | gunzip <filename | dirname>: 压缩解压.gz
    - zip <dest> <source> | unzip <filename | dirname>: 压缩解压.zip
    - tar -zcvf <dest> <source> | tar -zxvf <source>: 压缩解压 .tar.gz
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
  - 权限
    - /etc/passwd: 用户配置文件, 每行含义 用户名:口令:uid:gid:注释/主目录/登录shell
    - /etc/shadow: 加密后的用户口令
    - /etc/group: 组配置文件, 每行含义 组名:口令:gid:组内用户列表
    - visudo: 修改sudo用户
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
    - ps -aux: 查看进程状态
  - 网络
    - netstat -a: 查询网络状态
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

fdisk gdisk parted grub

BIOS UEFI MSOS GPT

- 开机程序
  - BIOS
  - UEFI

- CMOS: DRAM, 记录主板参数, 系统时间,CPU电压与频率, 各项设备I/O地址与IRQ
- BIOS: ROM, 开机程序


- 磁区512Byte, 磁区4KB

BIOS/UEFI->MBR中的boot loader程序->操作系统

- boot loader
 1. 直接启动操作系统
 2. 提供选项, 转交给其他loader(多系统)

 grub, BIOS loader

- 每组分割槽第一个磁区为开机磁区(boot sector)

- MBR: 最多4组分割, 每组分割16Byte, 管理2T存储量
  - 第一磁区: 512Byte
    - 开机启动记录MBR: 446Byte, 内含开机管理程序(boot loader)
    - Primary与Extended分割表: 64Byte, 保存Primary分割记录与Extended分割记录, 每组记录16Byte, 最多4组, 延伸分割只能有一组
  - Logic分割表: 在延伸分割槽内, 记录逻辑分割记录, 每组记录16Byte

- GPT: 最多128组分割, 每组分割128Byte, 管理8ZB存储量
  - 第一磁区： 4KB
    - 开机启动记录MBR: 446Byte, LBA0
    - GPT表头记录: LBA1
    - 分割表: LBA2-33, 每个区块512Byte

NAT, SAMBA, MAIL, WEB, DHCP, FTP


CPU, 显卡, 主存, 辅存, 网卡, 总线, 其它设备
BIOS/UEFI, MBR开机管理程序, 操作系统
进程管理, 文件系统, 权限






