
# notes

我的学习笔记

我的第一个git仓库

- 

*hello*

~~~c
#include <stdio.h>

int main() {
  
}
~~~

## 命令行



* 常用命令行及作用

  1.ls :列出当前目录下的文件或文件夹。-l显示详细信息，-a显示所有文件包括隐藏文件

  2.cd:进入目录；cd..返回上一级

  3.pwd：显示当前工作目录的路径

  4.mkdir：创建新目录

  5.rm：删除文件或目录；可以使用-i在删除前确认

  6.cp：复制文件或目录；可以使用-r选项递归复制目录

  7.kill:结束进程

  8.clear；清空终端屏幕

  9.find:寻找文件

***

## mark down的用法

1. 标题

   #代表h1

   ##代表h2

   ###代表h3

   以此类推直到h6

   h1是最大的标题

   只有在#后面加上空格才能使用

2. 引用

   在想要重点强调某一点处时用>+空格即可

   > 就像这样即可高亮

3. 分段

   在mark down中分段时遇到类似标题可以前后保留一个空行就能够分段了

4. 插入链接或图片

   在[]里加入文字然后使用（），在（）内加入链接即可使用

   使用图片与使用链接的方法一样，只用在[]前加入！就是图片的插入

5. 列表

   无序列表使用*或+或-标识

   有序列表使用数字加.再加空格即可

6. 注意事项

   +与-渲染出来的是空心标识

   *是实心

   例如：

   + 是+与-

     * 是*的

     标识也会自动改变产生区别以供区分。

7. 分割线

   三个*是分割线

   三个-也是分割线

   例如

   ***

   ---

8. 强调

   对某一部分进行强调的话使用*或者-包裹即可

   一边使用一个是斜体，一边使用两个是加粗

   例如

   **斜体*

   **加粗**

9. 插入代码块

   ~~~include 
   ~~~

   三个～即可

10. 一些符号需要与反斜线联合

11. 删除线

    使用~~来包裹

    例如

    这是正常的文本。
    ~~这是被删除的文本。~~
    
    要用英文的~。

### git学习

在终端上使用git commit -a -m“信息”

再使用git push origin(远程仓库名字) main（分支名）