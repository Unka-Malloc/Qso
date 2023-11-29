# io\_uring

io\_uring is a part of Linux kernel.

mmap -> share memory between user and kernel space

Memory Barrier

Submission Queue Ring: User submit entries into SQ.

Completion Queue Ring: Kernel returns results to CQ.

1. Aim to: Reduce system calls.
2. Submission Queue Ring (SQ\_Ring) and Completion Queue Ring (CQ\_Ring) are shared queues between user space and kernel space.
3. User - Submit into the Submission Queue Ring.
4. Kernel - Return results to the Completion Queue Ring.

{% embed url="https://github.com/axboe/liburing/wiki/io_uring-and-networking-in-2023" %}

{% embed url="https://zhuanlan.zhihu.com/p/582318316" %}

{% embed url="https://github.com/0voice/kernel_new_features/tree/main/io_uring" %}

{% embed url="https://nan01ab.github.io/2019/05/io_uring.html" %}

{% embed url="https://thenewstack.io/how-io_uring-and-ebpf-will-revolutionize-programming-in-linux/" %}

{% embed url="https://arthurchiao.art/blog/intro-to-io-uring-zh/" %}

{% embed url="https://www.byteisland.com/io_uring%EF%BC%881%EF%BC%89-%E6%88%91%E4%BB%AC%E4%B8%BA%E4%BB%80%E4%B9%88%E4%BC%9A%E9%9C%80%E8%A6%81-io_uring/" %}

{% embed url="https://www.byteisland.com/io_uring%EF%BC%882%EF%BC%89-%E4%BB%8E%E5%88%9B%E5%BB%BA%E5%BF%85%E8%A6%81%E7%9A%84%E6%96%87%E4%BB%B6%E6%8F%8F%E8%BF%B0%E7%AC%A6-fd-%E5%BC%80%E5%A7%8B/" %}

{% embed url="https://cloud.tencent.com/developer/article/1790806" %}
