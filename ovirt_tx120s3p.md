download latest ovirt (centos 8.5)

download mptsas drivers disk
https://elrepo.org/linux/dud/el8/x86_64/dd-mptsas-3.04.20-6.el8_5.elrepo.iso

attach centos iso as cd
attach driver as dvd

on installation screen, add kernel parameter inst.dd

ERROR: could not insert 'iw_cxgb4': Invalid argument 


1. try with mpt for 8_3 and mount it as cd (we have 2x cd)
unknown symbol in module, or unknown parameter

switch to ovirt older image (ovirt 4.4.6 )
unknown symbol in module, or unknown parameter


trying mpt3sas

could not insert mpt3sas invalid argument

trying  - THIS WORKS
CentOS-8.3.2011-x86_64-dvd1
dd-mptsas-3.04.20-4.el8_3.elrepo.iso

trying 8.5 - invalid argument

after installing os

change repo or

[root@rhv2 yum.repos.d]# sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-Linux-*
[root@rhv2 yum.repos.d]# sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.epel.cloud|g' /etc/yum.repos.d/CentOS-Linux-*


or migrate to rocky 
https://www.getpagespeed.com/server-setup/how-to-fix-dnf-after-centos-8-went-eol


block updates:
/etc/dnf/dnf.conf
exclude=kernel* kmod-kvdo* 
?maybe centos-linux-release* rocky-release*


dnf install https://resources.ovirt.org/pub/yum-repo/ovirt-release44.rpm
dnf install cockpit-ovirt-dashboard


add ttyS0 to kernel params
http://chrisreinking.com/how-to-enable-serial-console-output-in-centos/