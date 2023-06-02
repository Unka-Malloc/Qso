# Thread

线程 (Thread) 是 CPU 执行(Execute) 的最小单位. Thread 是 Process 的一部分, Thread 不具备 寻址空间(Address Space), 因此 Thread 只能依托于 Process 存在. 如果 Thread 崩溃, 那么负责管理这个线程的 Process 也会崩溃.&#x20;

#### **Address Space**

Since all threads share the same address space of the process, a thread A can get access to the local variables of another thread B as long as A and B are in the same process.

{% hint style="info" %}
Threads 共享 Process 的 Address Space, 但 Threads 在多数情况下会维护各自的 堆栈(Local Variables). 线程是否能访问同一进程下其它线程的堆栈, 则是完全由不同应用的 具体实现(Implementation) 决定的. 现实中, 只有一部分编程语言允许跨线程访问堆栈.
{% endhint %}
