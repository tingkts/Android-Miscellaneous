## Log level

```
    Verbose        2
    Devug          3
------------------------------------------------
    Info           4    <default log level>
    Warn           5
    Error          6
    Assert, WTF    7
```

<br/>

## Enable debug log



|              |                                                     |
|--------------|-----------------------------------------------------|
| uboot        | #define DEBUG                                       |
| kernel       | 1). #define DEBUG <br/> 2). modify printk log level |
| native ALOGD | #define LOG_NDEBUG 0                                |



<br/>

## Reference


◤ &nbsp; kernel

  &nbsp;&nbsp;&nbsp;&nbsp; ╴ [Modify kernel log level to 8 in uboot](./ref/0001-Modify-log-level-to-8-uboot-pass-to-kernel.patch)

  &nbsp;&nbsp;&nbsp;&nbsp; ╴ [Modify kernel printk CONSOLE_LOGLEVEL_DEFAULT](./ref/kernel.printk.printk.c.diff)

  ```
  root@zoey-gx05:~# cat /proc/sys/kernel/printk
  8 4 1 7

  ```

◤ &nbsp; native ALOGD, LOGD

  &nbsp;&nbsp;&nbsp;&nbsp; ╴ [ANDROID中C++层打开ALOGV打印的LOG开关 - 奔跑的蜗牛 - CSDN博客](https://blog.csdn.net/yu741677868yu/article/details/80682182)

  &nbsp;&nbsp;&nbsp;&nbsp; ╴ [enable log of /system/bt](./ref/0001-DON-T-MERGE-debug-log-only-of-system-bt.patch)

  &nbsp;&nbsp;&nbsp;&nbsp; ╴ [NDEBUG](http://aosp.opersys.com/xref/android-10.0.0_r47/search?q=NDEBUG&defs=&refs=&path=%22.+mk%22&hist=&type=&project=art&project=bionic&project=bootable&project=build&project=cts&project=dalvik&project=developers&project=development&project=device&project=external&project=frameworks&project=hardware&project=kernel&project=libcore&project=libnativehelper&project=packages&project=pdk&project=platform_testing&project=sdk&project=system&project=test&project=toolchain&project=tools)
