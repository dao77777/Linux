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
      - NTFS
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
- /proc/cpuinfo: cpu的详细信息
- /etc/os-release: linux发行版详细信息
- 硬盘
  - /dev/sd[a-p]: SCSI/SATA/USB
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
  - uname -r: 查看linux内核版本
- script
## 网络
## 虚拟机
- VirtualBox
- VMWare
- KVM(Linux自带)
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

BIOS UEFI MSOS GPT




