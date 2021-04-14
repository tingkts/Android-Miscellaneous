
[Download Source](https://busybox.net/downloads/)

</br>

Step :

  &ensp;＃ export arm cross compile toolchain

	export PATH=$PATH:~/aosp/android9/prebuilts/gcc/linux-x86/arm/arm-linux-androideabi-4.9/bin

  &ensp;＃ select android2_defconfig

	CONFIG_CROSS_COMPILER_PREFIX="arm-linux-androideabi-"

	CONFIG_SYSROOT="~/aosp/android10/prebuilts/ndk/current/platforms/android-28/arch-arm"


  &ensp;＃ `make menuconfig`

            Build Options --->

                [*] Build BusyBox as a static binary(no shared libs)



            Installation Options --->

                [*] Don't use /usr


  &ensp;＃ `make`

　&ensp;&ensp;May encounter several times of build break, need to be fixed case by case.


</br>
</br>

Ref :

 &ensp; [Android版busybox编译 CSDN/skdev](https://blog.csdn.net/skdev/article/details/45094637)

 &ensp; [在Android模拟器中安装busybox CSDN/very_on](https://blog.csdn.net/c_z_w/article/details/58585435?ops_request_misc=%25257B%252522request%25255Fid%252522%25253A%252522161009424816780277054516%252522%25252C%252522scm%252522%25253A%25252220140713.130102334..%252522%25257D&request_id=161009424816780277054516&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-4-58585435.first_rank_v2_pc_rank_v29&utm_term=build%20busybox%20in%20android)

 &ensp; [Android 7.1.1 下 Busybox 编译过程记录 CSDN/导数题](https://blog.csdn.net/daoshuti/article/details/69384820?ops_request_misc=%25257B%252522request%25255Fid%252522%25253A%252522160992266616780281236469%252522%25252C%252522scm%252522%25253A%25252220140713.130102334.pc%25255Fall.%252522%25257D&request_id=160992266616780281236469&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_v2~rank_v29-2-69384820.first_rank_v2_pc_rank_v29&utm_term=build%20busybox%20in%20android)

