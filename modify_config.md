---
layout: default
title: Modify Configuration files
description: 
---

 There are a few bits you may want to configure in preparation for this building a image, you will likely want to boot your hardware with FreeBSD and figure out:
 
 * Netowork interface naming format e.g. re0,en0 etc
 * Disk naming format for both your main OS disk and storage disk e.g ada0,da0 etc

#### Network Interfaces
Network interfaces are configured in ```overlay/etc/rc.conf.d/network```, it is assumed that 1 interface is a DCHP client for the IDS management and the rest are collection interfaces for Suricata; modify this as required. The default example is below

```bash
ifconfig_re0="DHCP" # IDS management
ifconfig_re1="up" # Collection
ifconfig_re2="up" # Not used but preped for collection or Netmap Bridge mode
```

#### Disks
NanaBSD needs the disk name defined in it configure file, in our case ```nanoIDS.conf```, this is defined under a NANO variable:

```bash
NANO_DRIVE="da0" # da0,ada0,mmc0 etc
```
In preparation for the storage disk installation it is worth modifying the ```cust_system_configuration``` function in the ```nanoIDS.conf``` file too:

```bash
# ADD FSTAB CONFIG
echo "#/dev/ada0p1	/data	ufs	rw	2	2" >> ${FSTAB_CONF}
```

This isn't required as you can modify the ```/etc/fstab``` after boot and save it persistantly using NanaBSD's ```save_cfg``` script

[back](./)