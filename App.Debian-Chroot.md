# DSM.debian-chroot.spk
## Brief
I have fixed bugs for fitting dsm6.1~6.2,according to [this issue](https://github.com/SynoCommunity/spksrc/issues/1910)
Tested on my ds3615xs, dsm6.2.

And then I upload to my dropbox, you can download here, link below.

which include debian-chroot.spk and python.spk

## Declares
0. I use volume1 as my application storage volume, many are volume1. so you should change it by yourself.

## Instructions !!!
***The Web UI Status Tab is not available.***

***Try to use shell totally***

SSH to your DSM6.x, and input those commands below

0. `/var/packages/debian-chroot/scripts/start-stop-status start # Start Command #if you check the auto start, when installing, this is not needed`
1. `chroot "/volume1/@appstore/debian-chroot/var/chroottarget" "/bin/bash" # Chroot In Command, change volume1 to your exact volume`

(`/volume1` should replaced by your own application storage volume number)

Now, you are in debian-chroot.
#### Adittional
Attention, on DSM6.x, this suite may not show running in DSM web interface like picture bellow, but you cant try the [1] command in ssh, you may find out that everything is ok.So, do not care about the web interface too much.At present I don't want to spend time on it, cause it is running well without web interface.

![Picture](https://raw.githubusercontent.com/OKit-Scripts-Projects/DSM.Customizations/master/images/DebianChrootStoppedButRealRunning.jpg)

### Additional Step for Services
If you need startup services, just add these kind of lines below in your ***Host DSM6.x***'s startup script in WebUI

0. `chroot "/volume1/@appstore/debian-chroot/var/chroottarget" "/etc/init.d/cron" "start"` ## for start cron service

So are the other services to start at DSM startup.

## Attention
0. Somebody meet some problem after installing this package, sometimes a Reboot is needed.

## Downloads
0. [Tenhow.debian-chroot.dsm6.[1/2].bromolow](https://www.dropbox.com/s/r4udr737knvv3jo/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.bromolow.zip?dl=0) [as DS3615xs] [Required by myself] √
0. [Tenhow.debian-chroot.dsm6.[1/2].braswell](https://www.dropbox.com/s/trav40yk89sghgc/tenhow.debian-chroot.dsm6.%5B1%20or%202%5D.braswell.zip?dl=0) [as DS3617xs] [Required by myself] 
0. [Tenhow.debian-chroot.dsm6.[1/2].apollolake](https://www.dropbox.com/s/aef5a6a70tparbc/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.apollolake.zip?dl=0) [as DS918+] [Required by lordvalium] √

   [python-2.7.dsm6.[1/2].apollolake](https://www.dropbox.com/s/m6hvsjs0mucmigx/python_apollolake-_2.7.14-19.spk?dl=0) [python-2.7 for DS918+]
0. [Tenhow.debian-chroot.dsm6.[1/2].cedarview](https://www.dropbox.com/s/85kzm6pgm90imnr/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.cedarview.zip?dl=0) [as DS1213+] [Required by Tao87-04] √
0. [Tenhow.debian-chroot.dsm6.[1/2].armadaxp](https://www.dropbox.com/s/04ivz8nfztg2fe9/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.armadaxp.zip?dl=0) [as RS815] [Required by DzikNsk] [No Feedback Yet]
0. [Tenhow.debian-chroot.dsm6.[1/2].88f628x](https://www.dropbox.com/s/w4psq4m4dgpdy4m/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.88f628x.zip?dl=0) [as DS212] [Required by balabalaman] √
0. [Tenhow.debian-chroot.dsm6.[1/2].armada375](https://www.dropbox.com/s/9lqepe0jf2dub44/debian-chroot_armada375-_8.4-7.spk?dl=0) [as DS215j] [Required by paul-xor] [Build by @destoron]

0. [Tenhow.debian-chroot.dsm6.[1/2].monaco](https://www.dropbox.com/s/3a6ocgfvdshzixr/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.monaco.zip?dl=0) [as DS216play] [Required by d4n1elchen] √
0. [Tenhow.debian-chroot.dsm6.[1/2].armada38x](https://www.dropbox.com/s/71p8e49dwbuv3zu/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.armada38x.zip?dl=0) [as DS216j] [Required by d4n1elchen] √
0. [Tenhow.debian-chroot.dsm6.[1/2].rtd1296](https://www.dropbox.com/s/6oc6ioc2c7abqti/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.rtd1296.zip?dl=0) [as DS418] [Required by gypittmann] [!Not Tested Yet!] 
0. [Tenhow.debian-chroot.dsm6.[1/2].avaton](https://www.dropbox.com/s/qroxml7bi7xy2oq/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.avoton.zip?dl=0) [as DS1817+] [Required by droidboxma] √
0. [Tenhow.debian-chroot.dsm6.[1/2].evansport](https://www.dropbox.com/s/2cmi66fp0mst949/tenhow.debian-chroot.dsm6.%5B1%20or%202%5D.evansport.zip?dl=0) [as DS214Play/DS415] [Required by rasmusmaagaard and g91720] 
0. [Tenhow.debian-chroot.dsm6.[1/2].qoriq](https://www.dropbox.com/s/t328ef3hyuhe9ko/debian-chroot_qoriq-_8.4-7.spk?dl=0) [as DS213+] [Required by Yagz] 

for qoriq

## Platform
As I am using ds3615xs, I compiled this.

If you need other platforms, just make an new issue, I would compile one for your platform later in my free time.

## Optimize
0. `apt update`
0. `apt upgrade`
0. `dpkg-reconfigure tzdata`
0. `apt install locales`
0. `dpkg-reconfigure locales`

## Request
If this repository helped, please give it a star, indicating this repository is helpfull.

Happy hacking! 

## References
0. [What_kind_of_CPU platform_does your_synology NAS have](https://www.synology.com/en-global/knowledgebase/DSM/tutorial/Compatibility_Peripherals/What_kind_of_CPU_does_my_NAS_have)



## Use With UPS
[autoac](https://github.com/OKit-Scripts-Projects/DSM.Customizations/blob/master/scripts/autoac) is a app for let synology or other computers poweroff when ac power failure. It a script for using with none communicated ups.


## Fish Shell
`apt install fish`

and then `exit` bash

`chroot "/volume1/@appstore/debian-chroot/var/chroottarget" "/usr/bin/fish"`

## Mount Volumes

`vim /var/packages/debian-chroot/scripts/start-stop-status`

go to `# Make sure we don't mount twice `
```
grep -q "${CHROOTTARGET}/volume1 " /volume1 || mount -o bind /volume1 ${CHROOTTARGET}/volume1
grep -q "${CHROOTTARGET}/volume2 " /volume2 || mount -o bind /volume2 ${CHROOTTARGET}/volume2
...
```

and go to `# Unmount `
```
umount ${CHROOTTARGET}/volume1
umount ${CHROOTTARGET}/volume2
...
```
then restart the chroot program
```
/var/packages/debian-chroot/scripts/start-stop-status stop
/var/packages/debian-chroot/scripts/start-stop-status start
```

enjoy.
