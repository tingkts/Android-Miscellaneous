§ &nbsp; Build kernel

- [Linux Kernel - How to obtain a particular version (right upto SUBLEVEL)](https://stackoverflow.com/questions/28136815/linux-kernel-how-to-obtain-a-particular-version-right-upto-sublevel)


```
git://git.kernel.org/pub/scm/linux/kernel/git/stable/kernel_imx.git
```

```
# Clone the kernel to your local machine
$ git clone git://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git
$ cd linux-stable

# Find the tag for the version you want
$ git tag -l | grep 3.18.1
v3.18.1

# Create a new branch with that tag
$ git checkout -b my3.18.1 v3.18.1
```

</br>

§ &nbsp; Query kernel version

 &nbsp; ▹  &nbsp;  from kernel source &nbsp; [⥂](https://www.cnblogs.com/super119/archive/2010/12/11/1902942.html)

 &nbsp;  &nbsp;  &nbsp; &nbsp; &nbsp; `head -n 5 Makefile`


 &nbsp; ▹  &nbsp;  from device console

 &nbsp;  &nbsp;  &nbsp; &nbsp; &nbsp; `uname -r`



</br>
§ &nbsp; De-compile DTB </br></br>

&emsp; ``dtc -I dtb ms5778-android-avb.dtb -O dts -o 123.dts``


</br>

§ &nbsp; Sample

- [Simple driver example for gpio pin control](./0001-example-simply-driver-of-gpio-pin-control.patch)



</br>
</br>

-------




§ &nbsp; Feature list

|       | feature |
| :-----| :---- |
| U-Boot | ▪&nbsp; function keys </br> &emsp; e.g. specific combined keys to enter recovery mode </br> ▪&nbsp; U-Boot logo|
| Recovery | ▪&nbsp; OTA update through USB disk |

