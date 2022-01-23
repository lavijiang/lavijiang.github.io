---
title: 面试题-mysql篇
date: 2022-01-11 10:24:20
tags:
---

## 一、常见面试侧重点

### 1.1、存储引擎

InnoDB与MyISAM区别
```
    事务：InnoDB支持，MyISAM不支持
    锁：InnoDB行级锁，MyISAM表级锁
    外键：InnoDB支持，MyISAM不支持
    表的行数：InnoDB不保存，MyISAM保存
```

### 1.2、索引  

什么是索引？作用和优缺点 
```
    定义：索引是对数据库表中字段数据进行排序的结构  
    作用：可以快速检索数据  
    优点：加快检索  
    缺点：维护成本、占用物理空间  
```

mysql基本的索引  
```
    唯一索引：索引值唯一，允许`空值`  
    主键：特殊的唯一索引，一个表只有一个主键，不允许空值  
    联合索引：多个列做索引，使用满足最左前缀原则（使用到索引的首个字段）  
    全文索引：查找文本中的关键字  
```

[b+树和b树的比较](https://stackoverflow.com/questions/870218/what-are-the-differences-between-b-trees-and-b-trees)
```
b+树：1、中间节点不存数据，因此一页可以存更多的key。增加扇出，并减少树的深度，减少io次数。
      2、全表扫描，b+树只需要叶子节点的顺序查找，然而b树需要中序遍历，会有更多的cache miss。
b+树：如果频繁使用的节点靠近根节点，会更方便
```

## 二、网上参考
https://www.cnblogs.com/toria/p/11204226.html
