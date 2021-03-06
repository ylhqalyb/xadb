# xadb
Android automated shell script, auto setup ida/gdb/lldb debug env, auto get device or app info and so on.

#### Install

- `git clone xadb_git_project;`
- `cd xadb` 
- `./install.sh the_android_sdk_path ` example:`./install.sh ~/xia0/android/sdk`
- If your shell is bash run: `source ~/.bash_profile`
- If your shell is zsh run :`source ~/.zshrc`

#### Command

> Tips：adb兼容内置的所有命令。在分别在pixel2 Android8 和pixel3 Android9上面测试通过。
>
> `mprop`只编译了64位的版本，若你为32位的设备，可以自行编译。
>
> 在source目录下面提供了mprop的源码及build脚本

**关于脱壳，之前基于frida的脱壳脚本只能脱一代壳且兼容性不高，就暂时没放出来。如果有大佬有比较好的方式，可以pr或者联系我完善下这部分。**

```
adb device   [imei]                              show connected android device basic info 
adb app      [sign/so/pid/apk/debug/dump]        show current app, debug and dump dex  
adb xlog     [package]                           logcat just current app or special package 
adb debug    [ida/ida64,lldb/lldb64, gdb/gdb64]  open debug and setup ida/lldb/gdb debug enviroment 
adb frida/64 start frida server on device        		 
adb pcat     [remote-file]                       copy device file to local 
adb pstree   show the process tree of device
adb -h       show this help usage 
adb update   update xadb for new version!
```



#### Project developers

- [xia0](https://github.com/4ch12dy)
- [hluwa](https://github.com/hluwa)



#### Update

- 2019-08-04/support pstree command: `adb pstree`

  ```
  |\
  |  1 root init
  |  |\
  |  |  567 root init subcontext u:r:vendor_init:s0 9
  |  |\
  |  |  568 root init subcontext u:r:vendor_init:s0 10
  |  |\
  |  |  569 root ueventd
  |  |\
  |  |  582 logd logd
  |  |\
  |  |  583 system qseecomd
  |  |   \
  |  |    606 system qseecomd
  |  |\
  |  |  585 system android.hardware.keymaster@4.0-service-qti
  |  |\
  |  |  586 system vndservicemanager /dev/vndbinder
  |  |\
  |  |  587 hsm citadeld
  ...
  ```

- 2019-08-05/support ida debug customize the debug port

  Usage:

  - `adb debug ida 23333` set debug port:23333

  - `adb debug ida` set 23946 as default debug port

  


#### Screeshot

![adb-device](https://github.com/4ch12dy/xadb/blob/master/screenshot/adb-device.png?raw=true)



![adb-app](https://github.com/4ch12dy/xadb/blob/master/screenshot/adb-app.png?raw=true)



![adb-app-so](https://github.com/4ch12dy/xadb/blob/master/screenshot/adb-app-so.jpeg?raw=true)



![adb-app-sign](https://github.com/4ch12dy/xadb/blob/master/screenshot/adb-app-sign.png?raw=true)



![adb-app-apk](https://github.com/4ch12dy/xadb/blob/master/screenshot/adb-app-apk.png?raw=true)



![adb-debug-ida](https://github.com/4ch12dy/xadb/blob/master/screenshot/adb-debug-ida.jpeg?raw=true)



![adb-debug-gdb](https://github.com/4ch12dy/xadb/blob/master/screenshot/adb-debug-gdb.png?raw=true)



![adb-debug-lldb](https://github.com/4ch12dy/xadb/blob/master/screenshot/adb-debug-lldb.png?raw=true)



![adb-frida](https://github.com/4ch12dy/xadb/blob/master/screenshot/adb-frida.png?raw=true)



![adb-xlog](https://github.com/4ch12dy/xadb/blob/master/screenshot/adb-xlog.png?raw=true)