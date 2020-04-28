[toc]

## 前言
最近接收一个新的ReactNative项目，里面有有关日历的操作需要了解数据库的知识，以前使用封装好的工具比较多，对具体的SQLite的操作已经不熟悉了，再次再归纳整理下相关知识。

## 基础脑图
![简洁结构](https://github.com/jiaozidev/resources/blob/master/image/2020-04/Android%20Cursor%20%E7%AE%80%E6%B4%81%E7%BB%93%E6%9E%84.png)

## 知识点

1. 是数据库查询的随机数据源，在使用时需要注意多线程同步问题。
```
/**
    * This interface provides random read-write access to the result set returned by a database query.
    * Cursor implementations are not required to be synchronized so code using a Cursor from multiple threads should perform its own synchronization when using the Cursor.
    * Implementations should subclass {@link AbstractCursor}.
*/
```

2. 获取数据
```
    fun obtainCursorData(cursor: Cursor) {
        val cursorRowCount = cursor.count
        if (cursorRowCount == 0) {
            // cursor中没有数据
        } else {
            cursor.moveToFirst()
            if (cursorRowCount == 1) {
                // TODO 使用get*()方法获取数据
            } else {
                while (cursor.moveToNext()) {
                    // TODO 使用get*()方法获取数据
                }
            }
        }
    }
```