# Raspberry Pi SD card create and backup routines

How to create SD card from PIXEL image and make a backup using open tools

## Download image of Raspbian Jessie with Pixel

Easy one, just download image of Raspbian Jessie with Pixel from project home:

[https://www.raspberrypi.org/downloads/raspbian/](https://www.raspberrypi.org/downloads/raspbian/)

The `.zip` version works just fine:

![image](https://cloud.githubusercontent.com/assets/14539/19022333/665162e4-88d6-11e6-9292-b3ec932a3dce.png)

## Download free, open source Etcher application

> Burn. Better.
Burn images to SD cards & USB drives, safe & easy.
[https://www.etcher.io/](https://www.etcher.io/)

![Etcher tool preview](https://www.etcher.io/static/images/product.gif)

## Create SD card iamge using Etcher

Just select downloaded image as source and emtpy SD card as target in Etcher:

![image](https://cloud.githubusercontent.com/assets/14539/19022368/3f1c04ee-88d7-11e6-9230-ab38b792a8fa.png)

## Make Backup

```bash
sudo dd if=/dev/disk2 | gzip > ~/Desktop/rasbian.img.gz
```

## Restore from Backup

Using CLI worked perfectly. Using Etcher has been failing to finish correctly (TBI).
CLI:
```bash
gunzip --stdout ~/Desktop/rasbian.img.gz | sudo dd of=/dev/disk2
dd: /dev/disk2: end of device
15523841+0 records in
15523840+0 records out
7948206080 bytes transferred in 3749.280981 secs (2119928 bytes/sec)
```

## Author
@peterblazejewicz
