***********************************************************************************
作者: 蒋守壮

个人邮箱: jiangshouzhuang@163.com

CSDN博客: http://blog.csdn.net/jiangshouzhuang
***********************************************************************************

Oracle2GP能够自动实现数据从Oracle迁移到Greenplum或HAWQ数据库。

实现的功能如下：

1. 数据库来源为Oracle

2. 能够自动将Oracle的DDL转换为Greenplum或HAWQ的语法，并自动在Greenplum中创建指定的schema和table

3. 自动实现从Oracle加载数据到Greenplum或HAWQ数据库

4. 目前暂时支持的作业类型为：

    * 更新：先truncate表再reload数据

    * 追加: 仅仅从Oracle抽取新增加的数据块

    * 复制：跟踪源数据的改变并应用这些改变(暂未实现)

    * 转换: 通过SQL命令在Greenplum或HAWQ中执行

5. 多线程动态调整作业数并行执行

6. 作业重复调度

7. 自动数据清洗

8. 对Greenplum自带工具gpfdist快速加载数据进行优化

安装步骤:

source oracle2gp_path.sh

bash oracle2gp_compile.sh

bash oracle2gp_install.sh


目前基于Oracle 11g和Greenplum 4.3.x.x完全测试。
