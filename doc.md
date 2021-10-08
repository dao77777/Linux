> **作者:** dao77777
> **创建日期:** 2021/10/8
> **更新日期:** 2021/10/8

- [鸟哥私房菜](http://linux.vbird.org/)
- UNIX环境高级编程
- UNIX网络编程

- 组成
  - CPU
    - ALU CU X MAR MDR IR PC
    - 主频
    - RISC, SPARC, PowerPC, ARM
    - CISC, x86
    - 位, 字节, 字长
    - Hyper-Threading HT
  - 主存
    - RAM
      - DRAM
        - SDRAM, DDR
      - SRAM
      - ROM
        - EEPROM
  - I/O设备
    - 辅存
      - HDD, SSD
      - 磁区, 磁轨, 磁柱
      - MSDOS, GPT
      - IOPS
    - 显卡
    - I/O地址, IRQ中断
  - 接口
    - 串口， 并口
    - 通用: USB, 雷电, SCSI, PS/2
    - 显卡: PCI, AGP, PCI-E
    - 显示器: D-Sub, DVI, HDMI, Display port
    - 网口: RJ-45
    - 硬盘: SATA, SAS, IDE, M.2

- Intel
  - QPI, DMI
- AMD
  - Hyper Transport
- cpu-z
- FSB

- BIOS
  - CMOS

- 硬件->内核->系统调用->应用程序
- NTFS


- UNIX
  - BSD
  - System V
  - Minix
  - Linux
    - RPM: RHEL Fedora CentOS SuSE OpenSuSE
    - DPKG: Ubuntu Debian B2D
    - Android

/proc/cpuinfo: cpu的详细信息
/etc/os-release: linux发行版详细信息
/usr/share/doc

- uname -r: 查看linux内核版本

- ssh 
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

- GNU
  - Emacs
  - GNU C(GCC)
  - GNU C Library(glibc)
  - Bash shell

- POSIX FHS LSB

- open source
  - Apache License 2.0
  - BSD 3-Clause "New" or "Revised" license
  - BSD 2-Clause "Simplified" or "FreeBSD" license
  - GNU General Public License(GPL)
  - GNU Library or "Lesser" General Public License(LGPL)
  - MIT license
  - Mozilla Public License 2.0
  - Common Development and Distribution License


- 权限
- tarball/rpm/dpkg/yum/apt
- vi
- shell
- 网络

- vscode
  - 插件
    - Auto Rename Tag
    - Bracket Pair Colorizer
    - C/C++
    - Code Runner
    - Live Server
    - Volar