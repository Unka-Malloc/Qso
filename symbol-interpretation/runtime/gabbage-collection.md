# Gabbage Collection

GC 领域有2种常见的 GC 方法: 1. 引用计数器(Reference Counting) 2. 跟踪收集器(Tracing Collector).&#x20;

现实情况是: 引用计数器(Reference Counting)无人问津, 但是每隔一段时间就会被重新发明一次. 而跟踪收集器(Tracing Collector)到处都是, 被Java, C# 作为核心机制.

#### JVM 垃圾回收 (堆内存)

{% embed url="https://www.sakuratears.top/blog/JVM%E5%A0%86%E5%86%85%E5%AD%98%E5%8F%8A%E5%9E%83%E5%9C%BE%E5%9B%9E%E6%94%B6%E7%AE%80%E4%BB%8B.html" %}

{% embed url="https://tech.meituan.com/2020/08/06/new-zgc-practice-in-meituan.html" %}

## ZGC (Slides)

{% embed url="https://cr.openjdk.org/~pliden/slides/ZGC-OracleDevLive-2020.pdf" %}
