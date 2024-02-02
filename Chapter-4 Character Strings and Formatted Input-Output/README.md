

### 字符串（character string）

在C语言中，没有专门字符串的变量类型，字符串存储在`char`类型的数组中。数组由连续的存储单元组成字符串中的字符存储在相领的存储单元中，每个单元存储一个字符。数组的末尾字符为`\0`，即空字符(null character)，其ASCII码值是0，用于标记字符串的结束。C中的字符串一定以空字符结束，所以数组的容量必须至少比待存储字符串中的字符数多1。

> scanf()在遇到第一个空白字符（空格、制表符或换行符）时就不再读取输入。

```c
#include <stdio.h>
#include <string.h>
#define PRAISE "What a super marvelous name!"
int main(void)
{
    char name[40];

    printf("What's your name?\n");
    scanf("%s", name);
    printf("Hello, %s. %s\n", name, PRAISE);

    printf("The phrase of praise has %d letters ",strlen(PRAISE));
    printf("and occupies %d memory cells.\n", sizeof PRAISE);
  
    return 0;
}
```

`strlen()` 函数给出字符串中的字符长度，`sizeof`则把末尾不可见的空字符也计算在内。另外`sizeof`是否使用圆括号取决于运算对象是类型还是特定量，类型时必须使用圆括号，如`sizeof(char)`。

字符串常量`"x"`与字符常量'`x`'不同，`"x"`是派生类型(char数组)，由两个字符组成x和空字符`\0`；`'x'`是基本类型char，

C预处理器：预处理器可以用来定义常量，语法为`#define NAME value`：

```c
#define PI 3.14
```

编译程序时，程序中所有的`NAME`都会被`value`替换。这样定义的常量也成为 **明示常量（manifest constant）**。

const 限定符：C90标准新增，用于限定一个变量为只读：

```c
const int MONTHS = 12; // MONTHS在程序中不可更改
```

 `limits.h` 中常用明示常量：

 `float.h`  中常用明示常量：

`printf`函数

一些常见的转换说明和各自对应的输出类型见下图：



