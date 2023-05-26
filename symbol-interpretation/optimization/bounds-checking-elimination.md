# Bounds-Checking Elimination

对于 数组(Array) | 元组(Tuple) | 列表(List) | 字符串(String) 等 允许使用索引(Index) 的集合类型(Colleciton), 进行索引之前必须先进行边界检查, 以确保索引(Index)不会越过集合的边界(Boundary).&#x20;

简单来说, 如果一个  高位索引(Higher Index) 被访问过一次, 那么这个索引(Higher Index)之前的低位索引(Lower Index) 是没有必要(Unnecessary)进行边界检查的(Bounds-Checking).

因为: 如果高位索引(Higher Index)存在, 那么低位索引(Lower Index) 必然不可能超出边界(Boundary).&#x20;

所以: 执行过高位索引(Higher Index)之后, 低位索引(Lower Index) 便不再需要执行边界检查.

```
x := ["a", "b", "c", "d", "e"];

// optimize ~> x := ("a", "b", "c", "d", "e");

x[2] // bounds check!
x[0] // bounds check eliminate!
x[4] // bounds check!
```

### Go

{% embed url="https://go101.org/article/bounds-check-elimination.html" %}
