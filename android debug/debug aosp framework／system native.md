
### [Debugging Native Android Platform Code ](https://source.android.com/devices/tech/debug)

stack unwinder : parse frame of native stack trace (call stack)
```
    ≥ android 8  crashdump32/64
    ≤ android 7  debuggerd

```



</br>

#### [Using Debuggers](https://source.android.com/devices/tech/debug/gdb)

</br>

android 11 </br>
{
-  Using `gdbclient.py` which directly setup both local desktop and remote android ready for lldb or gdb debugging.

```shell
    # lldb
    gdbclient.py -n system_server  (--setup-forwarding vscode)  --lldb

    # gdb
    gdbclient.py -n system_server  (--setup-forwarding vscode)  --no-lldb

    p.s. () is optional for using VS Code debugging.
```

❓ &nbsp;Using `gdbserver64` in the remote andorid, it seems to encounter the error,

```shell
    generic_x86_64:/ # pidof system_server
    3618

    generic_x86_64:/ # gdbserver64 :1234 --attach 3618
    /bin/sh: 3618: inaccessible or not found
    During startup program exited with code 127.
    Exiting
```

&ensp;➥ &nbsp;Use `gdbclient.py -n system_server --setup-forwarding gdb --no-lldb` instead.

</br>

⚠️⁉️ &nbsp;Android 11 can only start lldb, gdb failed!

}

</br>
</br>

__Actually trial__ ：

</br>

|                            | acloud &ensp; *1 | emulator </br> aosp_cf_x86_64_phone-userdebug | emulator </br> aosp_x86_64-eng | gdbclient.py | gdbserver64 &ensp; *2 |
| -------------------------- | :--------------: | :-------------------------------------------: | :----------------------------: | :----------: | :-------------------: |
| android-11.0.0_r45         |    failed !?     |                    failed!                    |               ✓               |  only lldb   |  failed!  &ensp; *3   |
| android-10.0.0_r47         |                  |                    failed!                    |               ✓               |   only gdb   |          ✓           |
| android-security-9.0.0_r72 |       n/a        |                      n/a                      |               ✓               |   only gdb   |          ✓           |

*1 ： `acloud create --local-image --local-instance`&ensp;&ensp;[➚](https://source.android.com/setup/start#create_acloud_instance)

*2 ： e.g. : `generic_x86_64:/ # gdbserver64 :12233 --attach 1721`


        ting@ting:/media/ting/Data-AOSP-3/android-9$ adb shell
        adb server version (41) doesn't match this client (40); killing...
        * daemon started successfully
        generic_x86_64:/ # pidof system_server
        1840
        generic_x86_64:/ # gdb
        gdbserver    gdbserver64
        generic_x86_64:/ # gdbserver64 :12233 --attach 1840
        Attached; pid = 1840
        Listening on port 12233

*3 ： Error message :

```
    generic_x86_64:/ # gdbserver64 :12055  --attach 654
    /bin/sh: 654: inaccessible or not found
    During startup program exited with code 127.
    Exiting
```



</br>
</br>
</br>

------

</br>

`readelf -s *.so`&ensp;:&ensp;info of stripped or unstripped binary&emsp;[➚](https://stackoverflow.com/questions/22682151/difference-between-a-stripped-binary-and-a-non-stripped-binary-in-linux)


```shell
    generic_x86_64:/ # readelf --help
    usage: readelf [-adhlnSsW] [-p SECTION] [-x SECTION] [file...]

    Displays information about ELF files.

    -a	Equivalent to -dhlnSs
    -d	Show dynamic section
    -h	Show ELF header
    -l	Show program headers
    -n	Show notes
    -p S	Dump strings found in named/numbered section
    -S	Show section headers
    -s	Show symbol tables (.dynsym and .symtab)
    -W	Don't truncate fields (default in toybox)
    -x S	Hex dump of named/numbered section

    --dyn-syms	Show just .dynsym symbol table
```
