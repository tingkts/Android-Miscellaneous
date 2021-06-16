
[Build AOSP](https://source.android.com/setup/build/building)

hmm :
```
    ting@ubuntu:~/aosp/android11$ source build/envsetup.sh
    ting@ubuntu:~/aosp/android11$ hmm

    Run "m help" for help with the build system itself.

    Invoke ". build/envsetup.sh" from your shell to add the following functions to your environment:
    - lunch:      lunch <product_name>-<build_variant>
                Selects <product_name> as the product to build, and <build_variant> as the variant to
                build, and stores those selections in the environment to be read by subsequent
                invocations of 'm' etc.
    - tapas:      tapas [<App1> <App2> ...] [arm|x86|mips|arm64|x86_64|mips64] [eng|userdebug|user]
    - croot:      Changes directory to the top of the tree, or a subdirectory thereof.
    - m:          Makes from the top of the tree.
    - mm:         Builds and installs all of the modules in the current directory, and their
                dependencies.
    - mmm:        Builds and installs all of the modules in the supplied directories, and their
                dependencies.
                To limit the modules being built use the syntax: mmm dir/:target1,target2.
    - mma:        Same as 'mm'
    - mmma:       Same as 'mmm'
    - provision:  Flash device with all required partitions. Options will be passed on to fastboot.
    - cgrep:      Greps on all local C/C++ files.
    - ggrep:      Greps on all local Gradle files.
    - gogrep:     Greps on all local Go files.
    - jgrep:      Greps on all local Java files.
    - resgrep:    Greps on all local res/*.xml files.
    - mangrep:    Greps on all local AndroidManifest.xml files.
    - mgrep:      Greps on all local Makefiles and *.bp files.
    - owngrep:    Greps on all local OWNERS files.
    - sepgrep:    Greps on all local sepolicy files.
    - sgrep:      Greps on all local source files.
    - godir:      Go to the directory containing a file.
    - allmod:     List all modules.
    - gomod:      Go to the directory containing a module.
    - pathmod:    Get the directory containing a module.
    - refreshmod: Refresh list of modules for allmod/gomod.

    Environment options:
    - SANITIZE_HOST: Set to 'address' to use ASAN for all host modules.
    - ANDROID_QUIET_BUILD: set to 'true' to display only the essential messages.

    Look at the source to view more functions. The complete list is:
    addcompletions add_lunch_combo allmod build_build_var_cache cgrep check_product check_type check_variant choosecombo chooseproduct choosetype choosevariant _complete_android_module_names core coredump_enable coredump_setup cproj croot _croot destroy_build_var_cache enable_zsh_completion get_abs_build_var getbugreports get_build_var getlastscreenshot get_make_command getprebuilt getscreenshotpath getsdcardpath gettargetarch gettop ggrep godir gogrep gomod hmm is isviewserverstarted jgrep key_back key_home key_menu lunch _lunch m make mangrep mgrep mm mma mmm mmma owngrep pathmod pez printconfig print_lunch_menu provision qpid rcgrep refreshmod resgrep runhat runtest sepgrep setpaths set_sequence_number set_stuff_for_environment sgrep should_add_completion smoketest source_vendorsetup startviewserver stopviewserver systemstack tapas tracedmdump treegrep _trigger_build validate_current_shell _wrap_build
```

m help :

```
    tingsung@ubuntu:~/aosp/android11$ m help
    The basic Android build process is:

    cd /home/tingsung/aosp/android11
    source build/envsetup.sh    # Add "lunch" (and other utilities and variables)
                                # to the shell environment.
    lunch [<product>-<variant>] # Choose the device to target.
    m -j [<goals>]              # Execute the configured build.

    Usage of "m" imitates usage of the program "make".
    See /home/tingsung/aosp/android11/build/make/Usage.txt for more info about build usage and concepts.

    Common goals are:

        clean                   (aka clobber) equivalent to rm -rf out/
        checkbuild              Build every module defined in the source tree
        droid                   Default target
        nothing                 Do not build anything, just parse and validate the build structure

        java                    Build all the java code in the source tree
        native                  Build all the native code in the source tree

        host                    Build all the host code (not to be run on a device) in the source tree
        target                  Build all the target code (to be run on the device) in the source tree

        (java|native)-(host|target)
        (host|target)-(java|native)
                                Build the intersection of the two given arguments

        snod                    Quickly rebuild the system image from built packages
                                Stands for "System, NO Dependencies"
        vnod                    Quickly rebuild the vendor image from built packages
                                Stands for "Vendor, NO Dependencies"
        pnod                    Quickly rebuild the product image from built packages
                                Stands for "Product, NO Dependencies"
        senod                   Quickly rebuild the system_ext image from built packages
                                Stands for "SystemExt, NO Dependencies"
        onod                    Quickly rebuild the odm image from built packages
                                Stands for "ODM, NO Dependencies"


    So, for example, you could run:

    cd /home/tingsung/aosp/android11
    source build/envsetup.sh
    lunch aosp_arm-userdebug
    m -j java

    to build all of the java code for the userdebug variant of the aosp_arm device.

```


