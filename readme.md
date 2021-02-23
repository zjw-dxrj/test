# 第一章 FreeRTOS 简介  

## FreeRTOS 特点  

FreeRTOS 是一个可裁剪的小型 RTOS 系统， 其特点包括：
● FreeRTOS 的内核支持抢占式， 合作式和时间片调度。
● SafeRTOS 衍生自 FreeRTOS， SafeRTOS 在代码完整性上相比 FreeRTOS 更胜一筹。
● 提供了一个用于低功耗的 Tickless 模式。
● 系统的组件在创建时可以选择动态或者静态的 RAM， 比如任务、消息队列、信号量、
软件定时器等等。
● 已经在超过 30 种架构的芯片上进行了移植。
● FreeRTOS-MPU 支持 Corex-M 系列中的 MPU 单元， 如 STM32F103。
● FreeRTOS 系统简单、小巧、易用， 通常情况下内核占用 4k-9k 字节的空间。
● 高可移植性，代码主要 C 语言编写。
● 支持实时任务和协程(co-routines 也有称为合作式、 协同程序， 本教程均成为协程)。
● 任务与任务、 任务与中断之间可以使用任务通知、消息队列、二值信号量、数值型信
号量、 递归互斥信号量和互斥信号量进行通信和同步。
● 创新的事件组(或者事件标志)。
● 具有优先级继承特性的互斥信号量。
● 高效的软件定时器。
● 强大的跟踪执行功能。
● 堆栈溢出检测功能。
● 任务数量不限。
● 任务优先级不限。  





# 第二章 FreeRTOS 移植  







# 第三章 FreeRTOS 系统配置  

FreeRTOS 的配置基本是通过在 FreeRTOSConfig.h 中使用“#define” 这样的语句来定义宏定义实现的。   

## 3.1 “INCLUDE_”开始的宏  

使用“INCLUDE_”开头的宏用来表示使能或除能 FreeRTOS 中相应的 API 函数， 作用就是用来配置 FreeRTOS 中的可选 API 函数的。比如当宏 INCLUDE_vTaskPrioritySet 设置为 0 的时候 表示不能 使用函数 vTaskPrioritySet() ， 当设置 为 1 的时 候就表示可 以使用函数vTaskPrioritySet()。这个功能其实就是条件编译 。

![image-20201201151135056](freertos.assets/image-20201201151135056.png)

## 3.2 “config”开始的宏  

“config”开始的宏和“INCLUDE_”开始的宏一样，都是用来完成 FreeRTOS 的配置和裁剪的，接下来我们就看一下这些“config”开始的宏。  







# 第四章 FreeRTOS 中断配置和临界段  

调 用 函 数 portDISABLE_INTERRUPTS() 关 闭 中 断 。 优 先 级 低 于configMAX_SYSCALL_INTERRUPT_PRIORITY 的中断都会被关闭，高于的不会受任何影响。  
