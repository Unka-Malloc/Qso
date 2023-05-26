# 线程池 (Thread Pool)

MySQL 服务器使用 线程池(Thread Pool) 并发模型, 每一个客户端连接对应一个子线程.

## 锁 (Lock)

### Type

*   #### Read Lock

    读取操作 => 不阻塞线程, 并发读取统一资源.
*   #### Write Lock

    写入操作 => 阻塞其它操作.

### Granularity

*   #### Table Lock

    开销较小. 对整张表格生效.
*   #### Row Lock

    开销极大. 对表格中的每一行数据生效.
