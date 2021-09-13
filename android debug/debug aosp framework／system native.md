[AOSP](https://source.android.com/) &nbsp;: &nbsp;[Using Debuggers](https://source.android.com/devices/tech/debug/gdb)

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


</br>
</br>
</br>

------

readelf -s *.so

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