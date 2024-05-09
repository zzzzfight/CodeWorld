## Character Device vs Block Device
> [how do character device or character special files work](https://unix.stackexchange.com/questions/37829/how-do-character-device-or-character-special-files-work) ✔
> 
> [what is a character device](https://askubuntu.com/questions/1021394/what-is-a-character-device) ✔
>
> [device driver basic](https://tldp.org/LDP/khg/HyperNews/get/devices/basics.html)
>
> [device file](https://en.wikipedia.org/wiki/Device_file)
>
> [character device drivers](https://linux-kernel-labs.github.io/refs/heads/master/labs/device_drivers.html)
>
> [The Linux Kernel Driver Interface](https://github.com/torvalds/linux/blob/master/Documentation/process/stable-api-nonsense.rst)
>
> [why is good to have all drivers in the kernel](https://www.reddit.com/r/linuxquestions/comments/ke76qa/why_is_it_good_to_have_all_drivers_in_the_kernel/?rdt=54989&onetap_auto=true&one_tap=true)
* 总结来说就是微内核/宏内核这两种观念：
   * 微内核（类似Minix）的架构是 硬件=>内核=>驱动 驱动部署在应用层，好处是内核与驱动隔离（内核不会受驱动影响）
   * 宏内核（类似Linux）的架构师 硬件=>内核，驱动耦合在内核之中，~~逻辑在于，驱动是从属于内核的，为内核提供操作外设硬件的方式，而非直接对用户提供接口~~（操作系统的定义）（这个往内核与驱动的概念引申了）
   * [The Tanenbaum-Torvalds Debate about device](../Other/device_debate.md)



* 字符设备类似于audio，显卡，键盘鼠标
* 块设备，具有输出缓冲和存储数据能力的设备 

> 猜想
1. 驱动是对设备的一套处理逻辑，通过驱动对设备进行读写等逻辑操作？
2. 系统如何知道设备可读可写？
   1. 通过中断/轮询确认设备读写就绪，还有一种机制是DMA。✔
   2. 当设备就绪时，通过某种方式去通知监听该设备的应用程序执行读写操作
   3. 对设备描述符设置flag或者load进就绪队列？（这些最终都是抽象成设备就绪，通知应用层可读写）
   4. （最终抽象成 应用层操作 => 调用驱动 => 设备执行修改）



> 理解


### 1. character device

### 2. block device