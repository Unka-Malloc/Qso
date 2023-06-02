# Gabbage Collection

GC 领域有2种常见的 GC 方法: 1. 引用计数器(Reference Counting) 2. 跟踪收集器(Tracing Collector).&#x20;

而现实情况是: 引用计数器(Reference Counting)无人问津, 但是每隔一段时间就会被重新发明一次. 而跟踪收集器(Tracing Collector)到处都是, 被Java, C# 作为核心机制.

