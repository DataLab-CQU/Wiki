# Linux练习

1. man XXX

   查看命令的帮助信息，遇到不会的命令时请优先使用这个。

   另一个查看帮助的方法是每个命令都有的XXX --help

2. 管道     |

   用于把一个命令的输出作为下一个命令的输入

   **示例：**

   cmd1 *.txt | cmd2 | cmd3

3. 输入输出重定向

   把输入或输出定向到另一个地方

   \> 输出重定向到一个文件或设备，覆盖原来的文件

   \>> 输出重定向到一个文件或设备，追加原来的文件

   \< 输入重定向到一个程序

   **示例：**

   ls -l \> ls_result 把ls的结果存在ls_result文件中

   ls -l \>> ls_result 把ls的结果追加到ls_result文件中

   mysql -uroot \< test.sql 在mysql控制台中执行test.sql中的语句

4. date

   获取时间的命令

   示例：

   格式化输出：

   date -> 2018年 4月18日 星期三 17时13分17秒 CST

   date +"%Y%m%d" -> 20180418 （年月日）

   date +"%H%M%S" -> 171250  (时分秒)

5. cat 

   连接文件，并输出到stdout

   使用方法：

   cat file_name1 file_name2...

   示例：

   cat fil1 file2 > file3 连接file1和file2，并输出到file3中

   cat file 1 >> file 2 把文件1的内容追加到文件2中

6. head 取出文件的头部数据

   tail 取出文件的尾部数据

   head -n 10 data.txt 从data.txt中取出前10行数据并输出到stdout中

7. more 类似于cat，一页一页地展示文件内容，按enter或者pagedown翻页，适合较大的文本文件

   less 类似more，但是more只能向下翻，less可以向上回滚

8. sort 给文本文件排序

   sort [-arg] … [file]...

   -t 指定分隔符，如果分隔符是'\t'（制表符，就是Tab键），需要写成-t$'-t'

   -kn,m[参数]，把第n列到第m列的数据按照[参数]中的方法来排列，默认是字典序增序排

   - n 按照整数排列（递增，不支持小数？待考证）
   - g 按照通用的计数方法来排
   - r 按照递减顺序来排

   sort –t$’-t‘ –k3r –k1,2n data.txt 把data.txt中的数据按照#分隔后，前两列按照数字顺序，先按第三列按减序排列，再按第一和第二列按照数字增序排列

   data.txt 如下

   3	2	1
   5	4	2
   1	7	3
   3	4	2

9. find 查找文件

   find path -name fn 在路径path下查找名为fn的文件，并将找到的路径输出到stdout

   find path -name fn -exec cmd {} \;对找到的每个文件执行cmd命令

10. grep 查找输入中符合条件的字符串

    grep 'pattern' filename 在文件filename中查找符合pattern的所有字符串

    加上-E参数，可支持正则表达式

11. top 查看系统资源的使用情况

    - 需要补充top界面都包含什么
    - 需要补充快捷键操作top界面，例如按照CPU使用情况进行从大到小排序

12. ps 查看当前运行的进程的信息

    ps axu | grep httpd 查找所有进程中进程包含httpd的进程

13. 向指定的进程发送信号

    kill -SIGKILL pid 强行杀死进程号为pid的进程

14. chmod 改变文件的权限

    文件的权限：

    r:读 w:写 x:执行

    本用户；用户所在组的其他用户；其他用户​