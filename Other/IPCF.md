## IPCF——一种核间通讯的方式

> [IPCF](https://www.nxp.com.cn/design/design-center/software/automotive-software-and-tools/inter-platform-communication-framework-ipcf:IPCF)

平台间通信框架（IPCF）是一个子系统，它支持位于同一芯片或不同芯片（在AUTOSAR™、FreeRTOS™等其他操作系统上运行）上的应用程序（在多个同构或异构处理内核上运行）通过各种传输接口（如共享内存和其他）进行通信。

IPCF公开了一个零拷贝API，用户可以直接使用该API来获得最高性能、最低开销和较低的CPU负载。驱动程序仅在本地存储器域中执行所有写入操作，确保本地和远程共享存储器不会相互干扰。

用户可以使用IPCF对其软件实施内存保护。




* 很泛