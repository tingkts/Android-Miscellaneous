### [AIDEGen](https://android.googlesource.com/platform/tools/asuite/+/refs/heads/master/aidegen/README.md)

</br>

Execute env. setup and lunch the specified target :

```
ting@ting:/media/ting/Data-AOSP/AOSP/android-11/aosp$ source build/envsetup.sh ; lunch aosp_x86_64-eng

```


- aosp/frameworks/base/services/core

```
    aidegen -i s -p /media/ting/Data-IDE/IDE/android-ide/android-studio/new-2021.09.03/android-studio-2020.3.1.24-linux/android-studio/bin
```


- aosp/frameworks/base/core/java

```
    aidegen -i s -p /media/ting/Data-IDE/IDE/android-ide/android-studio/new-2021.09.03/android-studio-2020.3.1.24-linux/android-studio/bin
```

</br>
</br>

```
ting@ting:/media/ting/Data-AOSP/AOSP/android-11/aosp$ aidegen --help
usage: aidegen [module_name1 module_name2... project_path1 project_path2...]

AIDEgen

This CLI generates project files for using in IntelliJ, such as:
    - iml
    - .idea/compiler.xml
    - .idea/misc.xml
    - .idea/modules.xml
    - .idea/vcs.xml
    - .idea/.name
    - .idea/copyright/Apache_2.xml
    - .idea/copyright/progiles_settings.xml

- Sample usage:
    - Change directory to AOSP root first.
    $ cd /user/home/aosp/
    - Generating project files under packages/apps/Settings folder.
    $ aidegen packages/apps/Settings
    or
    $ aidegen Settings
    or
    $ cd packages/apps/Settings;aidegen

positional arguments:
  targets               Android module name or path.e.g. Settings or
                        packages/apps/Settings

optional arguments:
  -h, --help            show this help message and exit
  -d {0,1,2,3,4,5,6,7,8,9}, --depth {0,1,2,3,4,5,6,7,8,9}
                        The depth of module referenced by source.
  -v, --verbose         Display DEBUG level logging.
  -i IDE, --ide IDE     Launch IDE type, j: IntelliJ, s: Android Studio, e:
                        Eclipse, c: CLion, v: VS Code. The default value is
                        'u': undefined.
  -p IDE_INSTALLED_PATH, --ide-path IDE_INSTALLED_PATH
                        IDE installed path.
  -n, --no_launch       Do not launch IDE.
  -r, --config-reset    Reset all saved configurations, e.g., preferred IDE
                        version.
  -s, --skip-build      Skip building jars or modules that create java files
                        in build time, e.g. R/AIDL/Logtags.
  -a, --android-tree    Generate whole Android source tree project file for
                        IDE.
  -e [EXCLUDE_PATHS [EXCLUDE_PATHS ...]], --exclude-paths [EXCLUDE_PATHS [EXCLUDE_PATHS ...]]
                        Exclude the directories in IDE.
  -V, --version         Print aidegen version string.
  -l LANGUAGE, --language LANGUAGE
                        Launch IDE with a specific language, j: Java, c:
                        C/C++, r: Rust. The default value is 'u': undefined.

INFO: To report the AIDEGen tool problem, please use this link: https://goto.google.com/aidegen-bug
```