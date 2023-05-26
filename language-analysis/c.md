# Syntax

Styio 大量借用了 C# 的设计.

### Comments

C# 使用 `//` 表示单行注释, `/* */` 表示多行注释.

```
// Single Line Comment

/*
 * Multiple
 * Line
 * Comment
 */
```

{% embed url="https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/tokens/comments" %}
\[1] Comment
{% endembed %}

### String Interpolation

{% embed url="https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/tokens/interpolated" %}
\[2] String Interpolation
{% endembed %}

### Verbatim Text

{% embed url="https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/tokens/verbatim" %}
\[3] Verbatim Text
{% endembed %}

### Raw String Literals

C# 和 Python 都可以使用 `"""` 来表示 原生字符串 (Raw String Literals)

```
"""
SELECT *
FROM ${TABLE}
WHERE ...
"""
```

{% embed url="https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/tokens/raw-string" %}
\[4] Raw String literals
{% endembed %}
