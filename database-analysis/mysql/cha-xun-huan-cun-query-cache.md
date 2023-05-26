# 查询缓存 (Query Cache)

MySQL 在 5.7 \~ 8.0 版本使用过 查询缓存 (Query Cache), 现在已经完全废除(Deprecated).

#### 机制

1. 对于 SELECT 操作, 将查询语句与哈希记录(Hash Table)匹配.
2. 如果 当前查询命中哈希记录 => 返回记录所对应的结果(Result).
3. 否则 => 返回查询结果, 并且存储当前查询的哈希值和对应的结果.&#x20;

#### 废弃原因

1. **Strict Hash.** 只有查询语句**完全一致**时, 哈希值才能成功匹配. 因此, 任何细微的差距都会导致无法命中缓存.&#x20;
2. **Read Only.** 任何对表格(Table)的修改都会导致对应的 Query Cache 失效.
3. **Reject Large Result.** 过大的查询结果会被缓存拒绝.
4. **Memory Block.** MySQL查询缓存绕过操作系统, 直接管理内存申请和释放. 这个操作会带来很高的性能开销.
5. **Lock Contention.** 查询缓存的使用会锁住当前线程.&#x20;

**经验总结**

1. 查询语句(Query)应该被解析(Parse)为抽象语法树(AST), 然后在语义(Semantic)层面上进行匹配.&#x20;
2.
3. **Best Practice:** 缓存应该尽可能靠近客户端 (The cache should be as close to the client as possible.)
