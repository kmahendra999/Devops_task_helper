For change how to change the swap value, when swap will come and hold the process

man sysctl

sysctl -a for view default things

sysctl -a | grep "swap"

sysctl -w vm.swappiness=40

sysctl -a | grep "swap"

vim /etc/sysctl.d/99-sysctl.conf me vm.swapiness=value and system reboot ys sysctl -p cmmand run karo

/etc/sysctl.d/sysctl.conf me he default files

###fsck command se file system check hota he if file system ext2,3,4 he to else xfs file system he to xfs_repair se check hota he.

+=============================

LVM concepts

Logical Voleme Manager



![image](https://github.com/kmahendra999/Devopsprojects/assets/9668316/1b58457c-e81c-4508-b9f7-7c7496a5ba04)


parted /dev/sdb

(parted)mklabel
NewDisk label type = msdos
primary / extended = primary
file system type ext2
start 1
end 1000M

(parted)mkpart
name = mylvm
type = ext2
start= 1
END = 1000MB

(parted)mkpart
partition type = primary
name = mylvm2
type = ext2
start= 1001MB
END = 2000MB

print

quit

REPL# udevadm settle

REPL# parted -s /dev/sdb set 1 lvm on
REPL# parted -s /dev/sdb set 2 lvm on

parted /dev/sdb
print

#### PV CREATE

pvcreate /dev/sdb1
pvcreate /dev/sdb2

pvdisplay dekhne ke liye

vgcreate DATABASE /dev/sdb1
vgextend DATABASE /dev/sdb2

pvdisplay dekhne ke liye

vgdisplay vg dekhne ke liye

lvcreate -L +1500M oracle DATABASE
-L for size
oracle name he
DATABASE vg konsa he

lvcreate -L +1500M mysql DATABASE


####format karna

mkfs.ext4 /dev/DATABASE/oracle
mkfs.xfs /dev/DATABASE/mysql

mkdir /mysql
mysql /oracle

mount /dev/DATABASE/oracle/oracle /oracle/
mount /dev/DATABASE/oracle/mysql /mysql/

df -h

===================

parted /dev/sdc
mklabel = msdos
partition type = primary
File system = ext2
start = 1
End = 5000MB
quit

REPL# udevadm settle
parted -s /dev/sdc/ set 1 lvm on
vgextend  DATABASE /dev/sdc1

vgdisplay

lvcreate -L +4000 MB -n GRRAS DATABASE

mkfs.ext4 /dev/DATABASE/GRRAS

mkdir /grras

mount /dev/DATABAS/GRRAS /grras/





