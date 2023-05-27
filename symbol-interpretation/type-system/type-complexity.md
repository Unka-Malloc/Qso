# Type Complexity

为了衡量(Measure) 类型系统(Type System) 的 复杂度(Complexity), 这里参照集合, 引入了 和类型(Sum Type) 与 积类型(Product Type) 的概念.&#x20;

## Sum Type

对于 X 和 Y 两种类型(Type), 如果 从 X 和 Y 派生的 Type Z 符合, 且 只符合 X 或 Y 其中的一种类型, 那么这种类型就是 和类型(Sum Type). `Z 的 复杂度 = X 的 复杂度 + Y 的复杂度`.

```
Type Z = X | Y
```

简单来说, 如果一个类型有两条分支, 而且它只有可能属于其单一的子分支(Either ... Or ...), 那么它就是和类型(Sum Type).

更通俗易懂的例子:&#x20;

我现在养了一只宠物, 它可能是 猫, 也可能是 狗, 也可能是 鸭子, 但它总不可能同时是 猫 + 狗 + 鸭子 的结合体, 这种动物就不存在, 那么这个类型就非常简单, 是和类型. 只需要遍历 (全部 猫的种类) + (全部 狗的种类) + (全部 鸭子的种类), 那么 就肯定能找到 我的宠物 究竟是什么 品种.&#x20;

最常见的 和类型(Sum Type), 就是 枚举类型 (Enum Type).

```rust
Option {
  cat = Cat::ACatBreed,
  dog = Dog::ADogBreed,
  duck = Duck::ADuckBreed,
};
```

## Product Type

对于 X, Y 两种类型(Type), 如果 从 X 和 Y 派生的 Type Z 符合 \[X, Y] 的组合(Combination), 那么这种类型就是 积类型(Product Type). `Z 的 复杂度 = X 的 复杂度 * Y 的复杂度`.

```
Type Z = [X, Y]
```

简单来说, 如果一个类型是由其它的多个属性组合(Attributes Combination)而成的, 那么这个类型就是积类型(Product Type).&#x20;

更通俗易懂的例子:

我现在有一只鸭子, 它要不然是生(Raw)的, 要不然是熟(Roast)的, 要不然是棕色(Brown)的, 要不然就是白色(White)的. 但是一个鸭子不管是生的还是熟的(`Raw`|`Roast`), 都不影响它的羽毛是什么颜色的(Feather Color). 这两种属性彼此独立, 又可以彼此结合, 组成鸭子的特征. 想要确认我的鸭子是什么样子的, 要穷举所有组合(Exhaustive Method) -> `{(Raw, Brown), (Roast, Brown), (Raw, White), (Roast, White)}` 因此, 这就是积类型(Product Type).&#x20;

```rust
enum class Meat {
  Raw,
  Roast,
};

enum class Color {
  Brown,
  White,
};

{(Meat::Raw, Color::Brown), 
 (Meat::Roast, Color::Brown), 
 (Meat::Raw, Color::White), 
 (Meat::Roast, Color::White)}
```

## Reduce Complexity

降低类型复杂度(Reduce Complexity), 可以提升类型推理速度(Accelerate Type Inference).

Rust 使用了 枚举(Enum)推理法则(Inference Principle). 把茫茫多的可能性降低到 2 种: `Result ::` `Ok` | `Err`, 以及 `Option ::` `Some` | `None`.&#x20;

`Result` 用于 判断函数运行过程是否出现了错误.&#x20;

`Option` 用于 判断返回结果的值是否是空值.

```rust
enum Result<R, E> {
  Ok(R),
  Err(E)
}

enum Option<T> {
  Some(T),
  None
}
```

和传统的 `Struct` 或 `Object` 对比, 使用枚举(Enum)类型的优点是:

1. **更小的内存占用**: 在分配内存时, 以枚举类型中较大的集合为上限(Upper Bound), 申请内存空间.
2. **不会出现 Undefined.** Object 的属性可能为空, 也可能为非法值, 一切皆有可能出错.
3. **更小的运行时开销**.&#x20;

## Usage

类型复杂度(Type Complexity) 主要有以下用途:

1. [类型推导(Type Inference)](../compilation/type-inference.md)
2. [泛型(Generic Type)](generic-type.md)

## Reference

{% embed url="https://mp.weixin.qq.com/s?__biz=MzI0OTQxNjQ4MA==&chksm=e9909da3dee714b51fd19086154a52f7edb0609dbb4bbe4a6302f78e72315f488d55f5913c55&cur_album_id=1851280371586252805&idx=1&mid=2247484396&scene=189&sn=d3163b58b71b888d79a35b8e31d0b48d#wechat_redirect" %}

{% embed url="https://zhuanlan.zhihu.com/p/122564699" %}
