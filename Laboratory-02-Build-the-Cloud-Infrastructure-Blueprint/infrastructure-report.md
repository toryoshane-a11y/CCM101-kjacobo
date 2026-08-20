os

PRETTY_NAME="Ubuntu 24.04.4 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04.4 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=noble
LOGO=ubuntu-logo

kernel version

6.8.0-138-generic

cpu model

Architecture:                x86_64
  CPU op-mode(s):            32-bit, 64-bit
  Address sizes:             39 bits physical, 48 bits virtual
  Byte Order:                Little Endian
CPU(s):                      1
  On-line CPU(s) list:       0
Vendor ID:                   GenuineIntel
  Model name:                Intel Xeon E312xx (Sandy Bridge, IBRS update)
    CPU family:              6
    Model:                   42
    Thread(s) per core:      1
    Core(s) per socket:      1
    Socket(s):               1
    Stepping:                1
    BogoMIPS:                7008.00
    Flags:                   fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 syscall nx rdtscp 
                             lm constant_tsc rep_good nopl xtopology cpuid tsc_known_freq pni pclmulqdq ssse3 cx16 pcid sse4_1 sse4_2 x2apic popc
                             nt tsc_deadline_timer aes xsave avx hypervisor lahf_lm cpuid_fault pti ssbd ibrs ibpb stibp tsc_adjust xsaveopt arat
                              md_clear
Virtualization features:     
  Hypervisor vendor:         KVM
  Virtualization type:       full
Caches (sum of all):         
  L1d:                       32 KiB (1 instance)
  L1i:                       32 KiB (1 instance)
  L2:                        4 MiB (1 instance)
  L3:                        16 MiB (1 instance)
NUMA:                        
  NUMA node(s):              1
  NUMA node0 CPU(s):         0
Vulnerabilities:             
  Gather data sampling:      Not affected
  Indirect target selection: Mitigation; Aligned branch/return thunks
  Itlb multihit:             KVM: Mitigation: VMX unsupported
  L1tf:                      Mitigation; PTE Inversion
  Mds:                       Mitigation; Clear CPU buffers; SMT Host state unknown
  Meltdown:                  Mitigation; PTI
  Mmio stale data:           Unknown: No mitigations
  Reg file data sampling:    Not affected
  Retbleed:                  Not affected
  Spec rstack overflow:      Not affected
  Spec store bypass:         Mitigation; Speculative Store Bypass disabled via prctl
  Spectre v1:                Mitigation; usercopy/swapgs barriers and __user pointer sanitization
  Spectre v2:                Mitigation; Retpolines; IBPB conditional; IBRS_FW; STIBP disabled; RSB filling; PBRSB-eIBRS Not affected; BHI Retpol
                             ine
  Srbds:                     Not affected
  Tsa:                       Not affected
  Tsx async abort:           Not affected
  Vmscape:                   Not affected

cpu cores

1

total ram

               total        used        free      shared  buff/cache   available
Mem:           1.9Gi       423Mi       832Mi       1.1Mi       815Mi       1.4Gi
Swap:          1.0Gi          0B       1.0Gi

disk capacity

Filesystem      Size  Used Avail Use% Mounted on
tmpfs           191M 1008K  190M   1% /run
/dev/vda1        19G  5.4G   13G  30% /
tmpfs           952M   84K  952M   1% /dev/shm
tmpfs           5.0M     0  5.0M   0% /run/lock
/dev/vda16      881M  117M  703M  15% /boot
/dev/vda15      105M  6.2M   99M   6% /boot/efi
tmpfs           191M  8.0K  191M   1% /run/user/1001

mounter filesystem

sysfs        on  /sys                      type  sysfs        (rw,nosuid,nodev,noexec,relatime)
proc         on  /proc                     type  proc         (rw,nosuid,nodev,noexec,relatime)
udev         on  /dev                      type  devtmpfs     (rw,nosuid,relatime,size=954836k,nr_inodes=238709,mode=755,inode64)
devpts       on  /dev/pts                  type  devpts       (rw,nosuid,noexec,relatime,gid=5,mode=620,ptmxmode=000)
tmpfs        on  /run                      type  tmpfs        (rw,nosuid,nodev,noexec,relatime,size=194892k,mode=755,inode64)
/dev/vda1    on  /                         type  ext4         (rw,relatime,discard,errors=remount-ro,commit=30)
securityfs   on  /sys/kernel/security      type  securityfs   (rw,nosuid,nodev,noexec,relatime)
tmpfs        on  /dev/shm                  type  tmpfs        (rw,nosuid,nodev,inode64)
tmpfs        on  /run/lock                 type  tmpfs        (rw,nosuid,nodev,noexec,relatime,size=5120k,inode64)
cgroup2      on  /sys/fs/cgroup            type  cgroup2      (rw,nosuid,nodev,noexec,relatime,nsdelegate,memory_recursiveprot)
pstore       on  /sys/fs/pstore            type  pstore       (rw,nosuid,nodev,noexec,relatime)
bpf          on  /sys/fs/bpf               type  bpf          (rw,nosuid,nodev,noexec,relatime,mode=700)
systemd-1    on  /proc/sys/fs/binfmt_misc  type  autofs       (rw,relatime,fd=32,pgrp=1,timeout=0,minproto=5,maxproto=5,direct,pipe_ino=2161)
hugetlbfs    on  /dev/hugepages            type  hugetlbfs    (rw,nosuid,nodev,relatime,pagesize=2M)
mqueue       on  /dev/mqueue               type  mqueue       (rw,nosuid,nodev,noexec,relatime)
debugfs      on  /sys/kernel/debug         type  debugfs      (rw,nosuid,nodev,noexec,relatime)
tracefs      on  /sys/kernel/tracing       type  tracefs      (rw,nosuid,nodev,noexec,relatime)
fusectl      on  /sys/fs/fuse/connections  type  fusectl      (rw,nosuid,nodev,noexec,relatime)
configfs     on  /sys/kernel/config        type  configfs     (rw,nosuid,nodev,noexec,relatime)
/dev/vda16   on  /boot                     type  ext4         (rw,relatime)
/dev/vda15   on  /boot/efi                 type  vfat         (rw,relatime,fmask=0077,dmask=0077,codepage=437,iocharset=iso8859-1,shortname=mixed,errors=remount-ro)
binfmt_misc  on  /proc/sys/fs/binfmt_misc  type  binfmt_misc  (rw,nosuid,nodev,noexec,relatime)
tmpfs        on  /run/user/1001            type  tmpfs        (rw,nosuid,nodev,relatime,size=194888k,nr_inodes=48722,mode=700,uid=1001,gid=1001,inode64)

hostname

ubuntu

ip address

1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute 
       valid_lft forever preferred_lft forever
2: enp1s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1450 qdisc fq_codel state UP group default qlen 1000
    link/ether 5e:10:2a:05:14:e3 brd ff:ff:ff:ff:ff:ff
    inet 172.30.1.2/24 brd 172.30.1.255 scope global dynamic noprefixroute enp1s0
       valid_lft 86308671sec preferred_lft 75519471sec
    inet6 fe80::bd27:b8e0:9599:47ca/64 scope link 
       valid_lft forever preferred_lft forever
3: docker0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1454 qdisc noqueue state DOWN group default 
    link/ether da:7f:04:58:ca:ba brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever
