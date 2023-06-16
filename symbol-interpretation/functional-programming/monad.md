# Monad

{% hint style="info" %}
当你开始思考Monad的时候, 你高尚的品格, 美好的人生, 就全都被毁掉了.
{% endhint %}

很多关于 Monad 的文章都非常复杂, 就好像和 函数式编程(Functional Programming) 有仇一样.&#x20;

如果要理解 Monad, 需要以下基础:

1. 遗忘 柯里化 (Currying)
2. 遗忘 函数式编程 (Functional Programming)
3. 遗忘 范畴论 (Category Thoery)
4. 遗忘 Functor + Applicative + Map
5. 遗忘 副作用 (Side Effect)
6. 遗忘 Haskell + IO
7. Monad 与基础知识无关, 你不需要任何基础

Monad 是只有一个变量的函数, 是的, 你可能无数遍看过这样的定义, 但你应该忘记它. 因为 Monad 虽然使用了 范畴论(Category Theory) 的概念, 但它的实际使用与 函数映射(`fmap`) 基本无关.&#x20;

当我们使用 Monad 的时候, 我们真正需要完成的事情是: <mark style="color:purple;">**使用编程语言向计算机解释应该如何把一个状态通过一系列不受外界干扰的变换后转换成另外一个状态.**</mark> 而这个状态变换的过程, 我们把它叫做: Monad.&#x20;

也就是说, 如果, 对于一个状态, 能够通过一些方式, 不受外界影响的, 使其在任何情况下, 都能确定地完成一个流程, 那么这个过程, 就叫做 Monad.&#x20;

Monad 不需要代码, 使用自然语言也可以清晰的表述 Monad:

```
假设用户指定一个整数值 x
将 x 的值 增加 1, 然后
将 x 的值 增加 2, 然后
将 x 的值 增加 3, 结束
流程结束
```

或者用 向右的箭头(`->`) 表示数据的流向:

<pre><code>x -> <a data-footnote-ref href="#user-content-fn-1">+1</a> -> <a data-footnote-ref href="#user-content-fn-2">+2</a> -> <a data-footnote-ref href="#user-content-fn-3">+3</a> -> y
</code></pre>

所以, Monad 本质上是一种设计理念, 表示状态的变化过程. 它的使用需要一个前提: 在一个巨大的系统中, 只有一个状态在改变, 而其它的一切, 都是固定的过程. 就像是流进管道的水, 我们需要它确定无疑的流向我们需要的位置, 也只有在这种情况下, 我们才需要 Monad 这样的设计模式.



[^1]: Applicative

[^2]: Applicative

[^3]: Applicative
