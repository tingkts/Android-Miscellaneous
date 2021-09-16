[Android Open Source Project](https://source.android.com/)

AOSP Code Search :
- [Android Code Search](https://cs.android.com/)
- [Opersys AOSP Portal](https://aosp.opersys.com/)
- [AndroidXRef](http://androidxref.com/)

</br>
</br>

Important topic :

- sepolicy

- init / vendor init service


</br>
</br>

Utility :

- launch IDE by [AIDEGen](./aidegen.md) ( ≥ android 11 )

- launch Emulator by [Acloud](https://android.googlesource.com/platform/tools/acloud/+/refs/heads/master/README.md)


</br>
</br>

Cross Compiler :

|android version| [build system](https://source.android.com/setup/build)   | tool chain |
|  ----  | ----  | --- |
| ≤ android 7  | [GNU Make](https://www.gnu.org/software/make/) | gcc / gdb|
| ≥ android 8  | [Soong build system](https://android.googlesource.com/platform/build/soong/+/refs/heads/master/README.md) | clang, llvm / lldb |