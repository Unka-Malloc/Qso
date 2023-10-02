---
description: Consistency, Availability, Partition Tolerance
---

# CAP Theorem

## Consistency

* Data is identical across all copies.
* Every request receives the most recent write (or an error).

Consistency 强调数据的不同备份之间的完全一致性. 如果一个系统保证了一致性, 那么对于需要获取的数据, 只需要访问它的任意一个存储位置, 就可以获得最近写入的数据.



### Paxos (Algorithm)

* Proposer
* Acceptor
* Learner



### Raft (Algorithm)

* Leader
* Candidate
* Follower

{% embed url="https://raft.github.io/" %}
Raft Consensus Algorithm
{% endembed %}

### Apache ZooKeeper

{% embed url="https://zookeeper.apache.org/index.html" %}
Apache ZooKeeper
{% endembed %}

## Availability

* Data is always accessible upon request.
* Every request receives a response (not an error), without the guarantee that it contains the most recent write.

## Partition Tolerance

## References

{% embed url="https://zhuanlan.zhihu.com/p/139973562" %}
分布一致性与共识算法简介
{% endembed %}
