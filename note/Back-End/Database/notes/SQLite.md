
## Reference

- [菜鸟教程 - SQLite](http://www.runoob.com/sqlite/sqlite-tutorial.html)

## SQLite

- SQLite数据存储类型：
    * `integer` : 整型值
    * `real` : 浮点值
    * `text` : 文本字符串
    * `blob` : 二进制数据（比如文件）

- 注 : 实际上`SQLite`是无类型的，就算声明为`integer`类型，还是能存储字符串文本（主键除外），建表时声明啥类型或者不声明类型都可以。


## C 函数接口

``` c
// 打开数据库
int sqlite3_open(
    const char *filename,   // 数据库的文件路径
    sqlite3 **ppDb          // 数据库实例
);

// 执行 SQL 语句
int sqlite3_exec(
    sqlite3*,                                   // 一个打开的数据库实例
    const char *sql,                            // 需要执行的SQL语句
    int (*callback)(void*,int, char**, char**), // SQL语句执行完毕后的回调
    void *,                                     // 回调函数的第1个参数
    char **errmsg                               // 错误信息
);

// 检查 SQL 语句的合法性（查询前的准备）
int sqlite3_prepare_v2(
    sqlite3 *db,            // 数据库实例
    const char *zSql,       // 需要检查的SQL语句
    int nByte,              // SQL语句的最大字节长度
    sqlite3_stmt **ppStmt,  // sqlite3_stmt实例，用来获得数据库数据
    const char **pzTail
);

// 查询一行数据
int sqlite3_step(sqlite3_stmt*); // 如果查询到一行数据，就会返回SQLITE_ROW

// 利用 stmt 获得某一字段的值（从下标 0 开始)
int sqlite3_column_int(sqlite3_stmt*, int iCol);                    // 整型数据
sqlite3_int64 sqlite3_column_int64(sqlite3_stmt*, int iCol);        // 长整型数据
double sqlite3_column_double(sqlite3_stmt*, int iCol);              // 浮点数据
const void *sqlite3_column_blob(sqlite3_stmt*, int iCol);           // 二进制文本数据
const unsigned char *sqlite3_column_text(sqlite3_stmt*, int iCol);  // 字符串数据
```