# Destructor

析构函数(Destructor) 和 构造函数(Constructor) 对应, 都是面向对象编程(OOP)的基本概念.&#x20;

其中, Constructor 在 Object 被创建的时候调用, 而 Destructor 在 Object 被销毁的时候调用.

在 C++ 中, Destructor 使用 `~` 标注, 并且拥有与 Class Name 相同的名称, 例如 `String` 对应的Destructor 为 `~String()`.

基类(Base Class) 的 Destructor 不会被 子类(Sub-Class) 继承(Inherit).&#x20;

Destructor 可能被以下事件触发:

1. 本地变量(Local Variable) 超出作用域(Scope), 对象的生命周期结束.
2. 显式调用(Explicitly Invoke) `delete` 关键字 释放了 使用 `new` 关键字 创建的 Object.
3. 全局对象(Global Object) 和 静态对象(Static Object) 在 程序结束前 调用 Destructor.
4. 显式(Explicitly) 调用(Invoke) Destructor, 通常用于对指针地址(Pointer Address)的清理.&#x20;

#### 析构顺序 (Sequence)

以下是对多级继承对象的析构顺序:

1. 判断: 派生类 和 基类 的 Destructors 是否都为 虚函数(Virtual)?
2. 判断: 派生类 是否被 Auto Cast 成 基类?
3. Auto Cast (派生类 -> 基类) & 派生类 `virtual ~` & 基类 `virtual ~` => 从派生类开始, 沿继承链从下向上, 依次调用所有的 Virtual Destructor.
4. Auto Cast (派生类 -> 基类) & 派生类 实现 Destructor & 基类 实现 Destructor  => 直接调用基类的 Destructor.
5. `delete` 派生类 & 派生类 实现 Destructor & 基类 实现 Destructor  => 从派生类开始, 沿继承链从下向上, 依次调用所有的 Destructor.

## Reference

{% embed url="https://github.com/MicrosoftDocs/cpp-docs/blob/main/docs/cpp/destructors-cpp.md" fullWidth="false" %}
\[1] Microsoft Docs: C++ Destructor
{% endembed %}

{% embed url="https://harttle.land/2015/06/22/cpp-object-lifecycle.html" %}
\[2]&#x20;
{% endembed %}
