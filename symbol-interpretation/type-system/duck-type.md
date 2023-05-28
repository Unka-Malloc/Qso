# Duck Type

鸭子类型(Duck Type) 是一种 用 组合(Composition) 替代 继承(Inheritance) 以实现 低耦合多态(Polymorphism) 的现代设计模式.&#x20;

Duck Type 的特点就是一把梭哈, 经常被使用在 泛型(Generic Type) 中. 做 加法(Addition) 的时候, 不管是 整数(Integer) 还是 小数(Float / Double), 都加起来就完事儿了, 根本不需要区分类型, 反正都要加起来. 从各种层面上来说, Duck Type 都非常符合直觉, 也非常简单.

Duck Type 为 功能修改(Modification) 提供了最大的 灵活性(Flexibility). 使用 Duck Type 意味着 应用程序只关注于 Object 是否含有需要使用的 参数(Attribute) 或 函数(Function), 而不关注 Object 本身的语义差异(Semantic Distinction).&#x20;

在 面向对象编程(Object-Oriented Programming) 中, Duck Type 以 继承多个抽象接口(Inherit Abstact Interfaces) + 组合(Composition) 的方式实现.&#x20;

在 Go, Rust 等 新时代编程语言中, Duck Type 以 结构体(Struct) + 特征(Trait Implementation) 的方式实现, 继承(Inheritance) 已经极少使用.

Duck Type 是很常用的设计理念, 实现起来也非常简单:

1. 定义 抽象接口(Define Abstract Interface), 然后 为 抽象接口(Abstract Interface) 添加 抽象方法(Abstract Function).&#x20;

```java
interface DuckLike {
  public void GaGaGa();
}
```

这样的构造允许我们做出一个永远正确的假设: 任何实现该抽象接口的方法都必定可以被调用特定的抽象方法. 在这个例子中, 任何一个 像鸭子的(DuckLike) Variable 都必定 可以 嘎嘎叫 (GaGaGa).&#x20;

2. 把 抽象接口(Abstract Interface) 当作 类型(Type) 使用, 作为 参数(Argument) 传入 函数(Function).

```java
static void sound(DuckLike animal) {
    animal.GaGaGa();
}
```

现在开始, 不管是什么动物, 只要它 像鸭子(DuckLike), 那么它就开始 嘎嘎叫(GaGaGa).
