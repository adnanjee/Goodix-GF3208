# Goodix-GF3208 for kernel 5.0.0

This code is written by Jiangtao Yi, <yijiangtao@goodix.com> for goodix fingeprint sensor in android devices.
I am compiling this code for linux kernel 5.0.0 using Ubuntu 19.04.
The below function in kernel 5.0.0 only accepts two arguments. 
So I am removing first arguments from function as follows.

!access_ok(VERIFY_WRITE, (void __user *)arg, _IOC_SIZE(cmd)); to
!access_ok((void __user *)arg, _IOC_SIZE(cmd));

The code compiles successfully with the followin error on loading module
insmod: ERROR: could not insert module goodix.ko: Unknown symbol in module


