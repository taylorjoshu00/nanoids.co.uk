---
layout: default
title: Flash Image
description: 
---

Once NanoBSD has finished, successfully, compiling you will find a complete image in ```/usr/obj/nanobsd.nanoids/``` directory.
This image can be flashed onto the media of your choice, in my case I used a USB SD card reader and wrote the image to the SD card using the dd command:
```bash
joshua@optiplex:~/Development/NanoIDS/images$ dd if=nanoids.img of=/dev/sda
```

[back](./)