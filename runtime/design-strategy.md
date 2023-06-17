# Design (Strategy)

Styio 必须同时拥有以下特性:

1. **并行计算 (Parallel Computing)**. Styio 必须为 高性能计算(HPC) 提供原生的语法支持.&#x20;
2. **异步IO (Asynchronous IO)**. Styio 必须为 网络IO 和 文件IO 提供封装好的 **异步运行时**.&#x20;

## Parallel Computing

**并行计算(Parallel Computing)** 是 Styio 支持 数据库查询(Database Query), 流式计算(Stream Computing) 的方式.&#x20;

## **Asynchronous IO**

**异步IO (Asynchronous IO)** 是 Styio 支持 文件读取/写入(File Read / Write), 高并发网络服务(Highly Concurrent Web Service) 的方式.
