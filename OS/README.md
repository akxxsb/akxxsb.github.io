# 操作系统读书笔记

## 虚拟化

* 进程
  + 进程是对cpu的虚拟化。
  + 进程受限执行, 不能直接访问硬件，需要借助系统调用来实现。
  + 操作系统在进程运行时将执行权限交给进程，当发生中断或者系统调用时，执行流返回到内核，操作系统重新获得执行。
  
* 进程调度
  
* 虚拟内存
  + 地址空间是对物理内存的虚拟化

## 并发

* 线程
* 锁
  + 解决互斥访问的问题，保证原子性, 顺序性(指令可能被重新排序)和可见性(一个线程的操作对另一个线程可能不可见)。
  + 锁的实现, xchg原子交换, TestAndSet, TestAndSwap。
  + 常见的锁, 自旋锁, 互斥锁, 读写锁, 可重入锁。
  + 死锁发生的条件, 活锁, 锁的公平性。
* 条件变量
  + 用来解决同步问题，当条件不满足时让出cpu, 条件满足唤醒等待的线程
  + 一个条件变量只和一个条件绑定，用while来做条件判断，避免条件不满足的时候被唤醒。
  + 需要唤醒所有线程时用boardcast。
  
* 示例代码

```c
#include <stdio.h>
int main()
{
    printf("hello world\n");
    return 0;
}
```

* 信号量
  + P操作和V操作，P等待，V释放，初始化为1可以当成互斥锁来用。

## 持久化

* 磁盘构造，顺序io和随机io的性能差异原因
* 文件系统接口
