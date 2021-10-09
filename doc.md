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
- /proc/cpuinfo: cpu的详细信息
- /etc/os-release: linux发行版详细信息
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
  - uname -r: 查看linux内核版本
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




