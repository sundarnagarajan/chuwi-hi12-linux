List of useful diagnostic commands and packages they come from (in Ubuntu)

Command to use to generate table below for a list of commands:
```
for c in fdisk gdisk sfdisk sgdisk cfdisk cgdisk parted blkid \
blockdev hdparm pvs vgs lvs nvme lsscsi lsblk dmidecode \
biosdecode lshw lsusb lspci pastebinit alsa-info.sh; \
do \
echo -e "$(dpkg -S $(which $c))"; \
done \
| sed -e 's/^/|/' -e 's/:/ |/' -e 's/$/ |/
```


| Package | Command |
| ------- | -------------------------------------- |
|util-linux | /sbin/fdisk |
|gdisk | /sbin/gdisk |
|util-linux | /sbin/sfdisk |
|gdisk | /sbin/sgdisk |
|util-linux | /sbin/cfdisk |
|gdisk | /sbin/cgdisk |
|parted | /sbin/parted |
|util-linux | /sbin/blkid |
|util-linux | /sbin/blockdev |
|hdparm | /sbin/hdparm |
|lvm2 | /sbin/pvs |
|lvm2 | /sbin/vgs |
|lvm2 | /sbin/lvs |
|nvme-cli | /usr/sbin/nvme |
|lsscsi | /usr/bin/lsscsi |
|util-linux | /bin/lsblk |
|dmidecode | /usr/sbin/dmidecode |
|dmidecode | /usr/sbin/biosdecode |
|lshw | /usr/bin/lshw |
|usbutils | /usr/bin/lsusb |
|pciutils | /usr/bin/lspci |
|pastebinit | /usr/bin/pastebinit |
|alsa-utils | /usr/sbin/alsa-info.sh |
