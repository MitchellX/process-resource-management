# process-resource-management
操作系统进程与资源管理
# <br><b>主要内容：</b></br>
设计并实现一个基本的进程与资源管理器。该管理器能够完成进程的控制，如进程创建与撤销、进程的状态转换；能够基于优先级调度算法完成进程的调度，模拟时钟中断，在同优先级进程中采用时间片轮转调度算法进行调度；能够完成资源的分配与释放，并完成进程之间的同步。该管理器同时也能完成从用户终端或者指定文件读取用户命令，通过Test shell模块完成对用户命令的解释，将用户命令转化为对进程与资源控制的具体操作，并将执行结果输出到终端或指定文件中。
<br></br>
![](system_architecture.png)
# 总体设计
系统总体架构如图1所示，最右边部分为进程与资源管理器，属于操作系统内核的功能。该管理器具有如下功能：完成进程创建、撤销和进程调度；完成多单元 (multi_unit)资源的管理；完成资源的申请和释放；完成错误检测和定时器中断功能。
图1中间绿色部分为驱动程序test shell, 设计与实现test shell，该test shell将调度所设计的进程与资源管理器来完成测试。Test shell的应具有的功能：
*	从终端或者测试文件读取命令；
*	将用户需求转换成调度内核函数（即调度进程和资源管理器）；
*	在终端或输出文件中显示结果：如当前运行的进程、错误信息等。
图1最左端部分为：通过终端（如键盘输入）或者测试文件来给出相应的用户命令，以及模拟硬件引起的中断
