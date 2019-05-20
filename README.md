# Goodix-GF3208 for kernel 5.0.0

This code is written by Jiangtao Yi, <yijiangtao@goodix.com> for goodix fingeprint sensor in android devices.
I am compiling this code for linux kernel 5.0.0 using Ubuntu 19.04.
The below function in kernel 5.0.0 only accepts two arguments. 
So I am removing first arguments from function as follows.

!access_ok(VERIFY_WRITE, (void __user *)arg, _IOC_SIZE(cmd)); to
!access_ok((void __user *)arg, _IOC_SIZE(cmd));

This sensor uses SPI internface on android devices. So the code compiles successfully with following warnings

WARNING: "netlink_exit" [/home/adnan/Downloads/fingerprint/fingerprint/goodix.ko] undefined!
WARNING: "netlink_init" [/home/adnan/Downloads/fingerprint/fingerprint/goodix.ko] undefined!
WARNING: "gf_hw_reset" [/home/adnan/Downloads/fingerprint/fingerprint/goodix.ko] undefined!
WARNING: "gf_power_on" [/home/adnan/Downloads/fingerprint/fingerprint/goodix.ko] undefined!
WARNING: "gf_cleanup" [/home/adnan/Downloads/fingerprint/fingerprint/goodix.ko] undefined!
WARNING: "gf_power_off" [/home/adnan/Downloads/fingerprint/fingerprint/goodix.ko] undefined!
WARNING: "sendnlmsg" [/home/adnan/Downloads/fingerprint/fingerprint/goodix.ko] undefined!

The following error on loading module

insmod: ERROR: could not insert module goodix.ko: Unknown symbol in module

Conclusion:

Failed to test the module as module is not loading. Moreover it is useless too because the laptops use usb interface for this sensor.


