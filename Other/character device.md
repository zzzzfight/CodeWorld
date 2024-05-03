## Character Device vs Block Device
> [how do character device or character special files work](https://unix.stackexchange.com/questions/37829/how-do-character-device-or-character-special-files-work)
> 
> [what is a character device](https://askubuntu.com/questions/1021394/what-is-a-character-device)

* 字符设备类似于audio，显卡，键盘鼠标
* 块设备，具有输出缓冲和存储数据能力的设备 

> 猜想
1. 驱动是对设备的一套处理逻辑，通过驱动对设备进行读写等逻辑操作？
2. 系统如何知道设备可读可写？
   1. 通过中断/轮询确认设备读写就绪？
   2. 当设备就绪时，通过某种方式去通知监听该设备的应用程序执行读写操作
   3. 对设备描述符设置flag或者load进就绪队列？（这些最终都是抽象成设备就绪，通知应用层可读写）
   4. （最终抽象成 应用层操作 => 调用驱动 => 设备执行修改）

> 理解
### 1. character device
### 2. block device