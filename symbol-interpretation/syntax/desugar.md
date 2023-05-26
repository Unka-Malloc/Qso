# Desugar

语法糖 (Syntax Sugar) 可以被 降级(Downgrade) 成 低级语言表示 (Low-Level Representation).

## For -> While

For Loop 优化成 While Loop 是常见的优化方式.&#x20;

```
@(i) -> [0..10] >> {
    ...
}
```

```
@(i) -> [...] >> {
    ...
    
    i = i + 1;
    ?(a == 10) :( {
        ! -> ();
    };
}
```
