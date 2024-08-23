---
layout: default
---

### NanoIDS; Suricata Intrusion Detection System based on NanoBSD
This project aims to build a NanoBSD image, chosen for its resiliance, into a fully fledged Suricata IDS/IPS using FreeBSD's [Netmap](https://man.freebsd.org/cgi/man.cgi?netmap(4)). The Operating system runs read-only and a second drive is mounted to enable persistant storage for Suricata logs, pcaps, configurations, datasets and datarep files. 

Currently this is running on a PC Engines APU2 under FreeBSD version 14.1 and Suricata version 7.0.6; the FreeBSD suricata package is updated frequently so I will try to follow this as closely as possible, time allowing.

### Several steps are need to build a working system

1. Install FreeBSD 14.1 with all ports tree and src
2. [Configure NanoBSD Enviroment](./configure_nanobsd_env.md)
3. [Make changes to configuration for your hardware](./modify_config.md)
4. [Build/fetch Suricata](./build_suricata.html).
5. [Build NanoIDS image](./build_nano_image.md)
6. [Flash Image onto hardware](./flash_image.md)

Updating a image is similar to the above except you only need to write a new slice to the NanaBSD install and set it as the active partition, this is acived easily using the NanoBSD ```update.sh``` script
 
 This website is still under development In the meantime check out the [repo](https://github.com/taylorjoshu00/NanoIDS)
