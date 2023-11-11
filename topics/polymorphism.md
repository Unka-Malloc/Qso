# Polymorphism

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## Inclusion



## Coersion



## Parametric



### Examples

*   **C++ Template (Static)**

    The types are taken as variables and then instantiated with particular type as needed while compiling.&#x20;

```cpp
template <typename T>
T Add(T a, T b) 
{
    return a + b;
}

int main()
{
    return Add<int>(1, 2); 
}
```

## Ad-hoc



### Examples:

*   **C++ Operator Overload (Dynamic)**

    The same operator shows different behaviours for different types.

```cpp
"A" + "B" // "AB" : String Concatenation
 1  +  2  //  3   : Integer Addition
```

*   **C++ Function Overload (Dynamic)**

    Dynamically choose which function to use while running.

```cpp
int get(int a) { return a; }
int get(int a, int b) { return a + b; }
int get(int a, int b, int c) { return a + b + c; }
...
```

## Sub-Type



### Examples:

*   C++ Virtual Table



## Articles

{% embed url="https://www.geeksforgeeks.org/ad-hoc-inclusion-parametric-coercion-polymorphisms/" %}

{% embed url="https://github.com/microsoft/proxy" %}

### FP:&#x20;

{% embed url="https://zhuanlan.zhihu.com/p/34201651" %}

### OOP:

{% embed url="https://wiyi.org/polymorphism-in-java.html" %}

{% embed url="https://zhuanlan.zhihu.com/p/582020718" %}
