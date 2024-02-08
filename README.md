# linux-disk-resize-on-VMBOX
Ubuntu Disk Resize and Extend on Oracle Virtual Box

linux partition resize vmbox extend
lvextend /dev/ubuntu-vg/ubuntu-lv /dev/sda3
resize2fs /dev/mapper/ubuntu--vg-ubuntu--lv


fix partition size first
sudo parted -l
pvscan
lvscan


add new disk to volumegroup
lvdisplay
lvmdiskscan -l
pvcreate /dev/sdb 
vgextend ubuntu-vg /dev/sdb
lvextend /dev/ubuntu-vg/ubuntu-lv /dev/sdb
resize2fs /dev/mapper/ubuntu--vg-ubuntu--lv  

