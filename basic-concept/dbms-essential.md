# DBMS Essential

## DBMS (Database Management System)

Database Management System (DBMS) 是一种经典的传统数据模型, 它对数据进行规范化, 并且统一管理. 保证数据的完整性, 稳定性和安全性是DBMS的主要目标.&#x20;

DBMS以事务类功能为核心, 即写入和读取数据时需要保持一致性, 这也叫做 **OLTP** (Online Transaction Processing). 得益于事务的读写一致性, DBMS最初, 且最适合的使用场景就是银行交易系统.&#x20;

#### 基本特性 (ACID)

1. 原子性(Atomicity)
2. 一致性(Consistency)
3. 隔离性(Isolation)
4. 持久性 (Durability)

#### 基础操作(CRUD)

1. 创建("Create -> `INSERT`")
2. 读取("Read -> `SELECT`")
3. 更新("Update -> `UPDATE`")
4. 删除("Delete -> `DELETE` | `DROP` | `TRUNCATE`")

### SQL

数据库(Database) 的 查询(Query) 依赖于 领域特定语言(DSL), 但不依赖于单一的领域特定语言.&#x20;

SQL (Structured Query Language) 是专注于DBMS领域的DSL, 也毫无疑问是现今为止最成功的DSL, 没有之一.  目前最常见的开源SQL关系型数据库引擎:

* **MySQL**
* **MariaDB** (Faster MySQL)
* **PostgreSQL**
* SQLite&#x20;

除此之外, 也有很多商业数据库引擎:

* Oracle Database Server
* SQL Server (Microsoft)

### 云服务 (Cloud Service)

RDS (Relational Database Service) 是互联网公司提供的基于关系型数据库的云服务(Cloud Service)托管. 使用 RDS 意味着将 可用性, 可靠性, 可扩展性 等 难题转移给云服务厂商, 让程序员专注于业务实现.&#x20;

现在压力给到云服务厂商, 它们面临着以下问题:

1. **I/O** 延迟 (**Latency**)&#x20;
2. 网络带宽容量 (**Network** Bandwidth **Capacity**)
3. 故障恢复 (**Recovery**)
4. 成本控制 (**Cost Control**)

大型服务器集群的管理和性能问题直接推动了 云原生(Cloud Native) 的架构革命, 同时也带来了新的开发(Develop) 部署 (Deploy) 模式.&#x20;

<figure><img src="../.gitbook/assets/rc24-cloud-native-evolution.avif" alt=""><figcaption><p>[1] <a href="https://www.oracle.com/cloud/cloud-native/what-is-cloud-native/">https://www.oracle.com/cloud/cloud-native/what-is-cloud-native/</a></p></figcaption></figure>
