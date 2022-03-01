

 

---

 

Set kernel logging LEVEL (1-9)

  - dmesg -n 1
  - dmesg -n 5 / dmesg -n 9


---

Disable SELinux

  - append kernel command line, androidboot.selinux=permissive  &ensp;[ 🔗 ](./DON-T-MERGE-disable-sepolicy.patch)


---


View system settings

  - adb shell settings  &ensp;[ 🔗 ](https://adbinstaller.com/commands/adb-shell-settings-5b670d5ee7958178a2955536)



---


Restart zygote

  ```
  setprop ctl.start zygote
  setprop ctl.stop zygote
  ```

---

Others :

  - procrank

  - systrace, traceview and dmtracedump

---
