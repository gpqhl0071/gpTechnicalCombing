MongoDB是一个跨平台的，面向文档的数据库，可提供高性能，高可用性和易扩展性。MongoDB致力于收集和文档的概念

# Database

数据库是用于收集的物理容器。每个数据库在文件系统上都有其自己的文件集。一台MongoDB服务器通常具有多个数据库。

# Collection

集合是一组MongoDB文档。它等效于RDBMS表。集合存在于单个数据库中。集合不强制执行架构。集合中的文档可以具有不同的字段。通常，集合中的所有文档都具有相似或相关目的。

# Document

文档是一组键值对。文档具有动态架构。动态模式意味着同一集合中的文档不需要具有相同的字段或结构集，并且集合文档中的公共字段可以保存不同类型的数据。


|RDBMS   | MongoDB  |
|---|---|
| Database	  | Database  |
| Table	  | Collection  |
| Tuple/Row	  | Document  |
| column	  | Field  |
| Table Join	  | Embedded Documents  |
| Primary Key	  | Primary Key (Default key _id provided by mongodb itself)  |

参考：[https://www.tutorialspoint.com/mongodb/mongodb_overview.htm](https://www.tutorialspoint.com/mongodb/mongodb_overview.htm)