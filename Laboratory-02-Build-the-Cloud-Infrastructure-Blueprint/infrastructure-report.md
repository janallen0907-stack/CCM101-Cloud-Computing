root@ubuntu:~$ cat /etc/os-release
echo "===== KERNEL ====="
uname -r
echo "===== CPU ====="
lscpu
echo "===== RAM ====="
free -h
echo "===== DISK ====="
lsblk
echo "===== FILESYSTEMS ====="
df -h
echo "===== MOUNTED FILESYSTEMS ====="
findmnt
echo "===== HOSTNAME ====="
hostname
echo "===== IP ADDRESS ====="
hostname -I 
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
===== KERNEL =====
6.8.0-136-generic
===== CPU =====
Architecture:                x86_64
  CPU op-mode(s):            32-bit, 64-bit
  Address sizes:             39 bits physical, 48 bits virtual
  Byte Order:                Little Endian
CPU(s):                      1
  On-line CPU(s) list:       0
Vendor ID:                   GenuineIntel
  BIOS Vendor ID:            Red Hat
  Model name:                Intel Xeon E312xx (Sandy Bridge, IBRS update)
    BIOS Model name:         RHEL-9.6.0 PC (Q35 + ICH9, 2009)  CPU @ 2.0GHz
    BIOS CPU family:         1
    CPU family:              6
    Model:                   42
    Thread(s) per core:      1
    Core(s) per socket:      1
    Socket(s):               1
    Stepping:                1
    BogoMIPS:                7008.00
    Flags:                   fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 syscall nx rdtscp lm constant_tsc 
                             rep_good nopl xtopology cpuid tsc_known_freq pni pclmulqdq ssse3 cx16 pcid sse4_1 sse4_2 x2apic popcnt tsc_deadline_timer aes xsave 
                             avx hypervisor lahf_lm cpuid_fault pti ssbd ibrs ibpb stibp tsc_adjust xsaveopt arat md_clear
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
  Spectre v2:                Mitigation; Retpolines; IBPB conditional; IBRS_FW; STIBP disabled; RSB filling; PBRSB-eIBRS Not affected; BHI Retpoline
  Srbds:                     Not affected
  Tsa:                       Not affected
  Tsx async abort:           Not affected
  Vmscape:                   Not affected
===== RAM =====
               total        used        free      shared  buff/cache   available
Mem:           1.9Gi       476Mi       779Mi       1.1Mi       815Mi       1.4Gi
Swap:          1.0Gi          0B       1.0Gi
===== DISK =====
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
vda     253:0    0   20G  0 disk 
|-vda1  253:1    0   19G  0 part /
|-vda14 253:14   0    4M  0 part 
|-vda15 253:15   0  106M  0 part /boot/efi
`-vda16 259:0    0  913M  0 part /boot
===== FILESYSTEMS =====
Filesystem      Size  Used Avail Use% Mounted on
tmpfs           191M 1000K  190M   1% /run
/dev/vda1        19G  5.4G   13G  30% /
tmpfs           952M   84K  952M   1% /dev/shm
tmpfs           5.0M     0  5.0M   0% /run/lock
/dev/vda16      881M  117M  703M  15% /boot
/dev/vda15      105M  6.2M   99M   6% /boot/efi
===== MOUNTED FILESYSTEMS =====
TARGET                         SOURCE      FSTYPE      OPTIONS
/                              /dev/vda1   ext4        rw,relatime,discard,errors=remount-ro,commit=30
|-/sys                         sysfs       sysfs       rw,nosuid,nodev,noexec,relatime
| |-/sys/kernel/security       securityfs  securityfs  rw,nosuid,nodev,noexec,relatime
| |-/sys/fs/cgroup             cgroup2     cgroup2     rw,nosuid,nodev,noexec,relatime,nsdelegate,memory_recursiveprot
| |-/sys/fs/pstore             pstore      pstore      rw,nosuid,nodev,noexec,relatime
| |-/sys/fs/bpf                bpf         bpf         rw,nosuid,nodev,noexec,relatime,mode=700
| |-/sys/kernel/debug          debugfs     debugfs     rw,nosuid,nodev,noexec,relatime
| |-/sys/kernel/tracing        tracefs     tracefs     rw,nosuid,nodev,noexec,relatime
| |-/sys/fs/fuse/connections   fusectl     fusectl     rw,nosuid,nodev,noexec,relatime
| `-/sys/kernel/config         configfs    configfs    rw,nosuid,nodev,noexec,relatime
|-/proc                        proc        proc        rw,nosuid,nodev,noexec,relatime
| `-/proc/sys/fs/binfmt_misc   systemd-1   autofs      rw,relatime,fd=32,pgrp=1,timeout=0,minproto=5,maxproto=5,direct,pipe_ino=2164
|   `-/proc/sys/fs/binfmt_misc binfmt_misc binfmt_misc rw,nosuid,nodev,noexec,relatime
|-/dev                         udev        devtmpfs    rw,nosuid,relatime,size=954832k,nr_inodes=238708,mode=755,inode64
| |-/dev/pts                   devpts      devpts      rw,nosuid,noexec,relatime,gid=5,mode=620,ptmxmode=000
| |-/dev/shm                   tmpfs       tmpfs       rw,nosuid,nodev,inode64
| |-/dev/hugepages             hugetlbfs   hugetlbfs   rw,nosuid,nodev,relatime,pagesize=2M
| `-/dev/mqueue                mqueue      mqueue      rw,nosuid,nodev,noexec,relatime
|-/run                         tmpfs       tmpfs       rw,nosuid,nodev,noexec,relatime,size=194892k,mode=755,inode64
| `-/run/lock                  tmpfs       tmpfs       rw,nosuid,nodev,noexec,relatime,size=5120k,inode64
`-/boot                        /dev/vda16  ext4        rw,relatime
  `-/boot/efi                  /dev/vda15  vfat        rw,relatime,fmask=0077,dmask=0077,codepage=437,iocharset=iso8859-1,shortname=mixed,errors=remount-ro
===== HOSTNAME =====
ubuntu
===== IP ADDRESS =====
172.30.1.2 172.17.0.1 
root@ubuntu:~$ 
