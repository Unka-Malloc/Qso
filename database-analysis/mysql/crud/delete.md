# Delete

## DELETE

1. DELETE 属于数据库事务性操作(DML)
2. DELETE 会触发 Delete Trigger.
3. DELETE 不会释放存储空间, 它只是标记了当前位置为空, 并且允许重用.
4. DELETE 支持Rollback.&#x20;
5. DELETE 可以使用 OPTIMIZE TABLE \[NAME] 强制释放存储空间.

## DROP

1. DROP 是数据库定义语言(DDL).
2. DROP 立即生效, 无法找回.
3. DROP 立即释放存储空间.

## TRUNCATE  \[TABLE]

1. TRUNCATE 是数据库定义语言(DDL).
2. TRUNCATE 会完全清空一张表格内的所有行.&#x20;
3. TRUNCATE 不支持回滚操作(Rollback).
4. TRUNCATE 会释放存储空间.

{% hint style="info" %}
删库跑路速度: DROP < TRUNCATE < DELETE
{% endhint %}
