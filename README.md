# C / Cpp

<!-- vim-markdown-toc GFM -->

* [Coding Style](#coding-style)
    - [命名](#命名)
        + [內容](#內容)
        + [大小寫](#大小寫)
        + [常用命名](#常用命名)
    - [排版](#排版)
    - [註解](#註解)
* [idom](#idom)

<!-- vim-markdown-toc -->

## Coding Style

### 命名

#### 內容

| global 完整 |   local 簡潔    |
| :---------: | :-------------: |
|    class    | member function |
|   struct    | member constant |
|  function   | member variable |
|    enum     |                 |
|    macro    |                 |
|  constant   |                 |
|  variable   |                 |

#### 大小寫

|  全大寫  | 首字母大寫 |  全小寫  |
| :------: | :--------: | :------: |
|   enum   |   class    | variable |
|  macro   |   struct   |          |
| constant |            |          |

#### 常用命名

|   概念   |    命名     |
| :------: | :---------: |
|   變數   | value / val |
|   資料   | data / dat  |
|   指標   |     ptr     |
|   陣列   |     arr     |
|   字串   |     str     |
|   數字   |     num     |
|   數量   |    size     |
| for 迴圈 |  i / j / k  |
|  前一個  | pre / prev  |
|  這一個  |     cur     |
|  後一個  | nxt / next  |

### 排版

### 註解

|    段落     |  單行  |
| :---------: | :----: |
| /\* ??? \*/ | // ??? |

## idom

-   輸入輸出

```c
#include <stdio.h>

int main(void) {
    printf("%05d\n", 999);

    return 0;
}
```

```c
#include <stdio.h>

int main(void) {
    double num = 99.99;

    int width, precision;
    scanf("%d %d", &width, &precision);

    printf("%*.*f\n", width, precision, num);

    return 0;
}
```

```c
#include <stdio.h>

int main(void) {
    int num;

    scanf("%*d %*d %d", &num);

    printf("%d\n", num);

    return 0;
}
```

-   運算子

```c
#include <stdio.h>

int main(void) {
    int num = 0;
    int a = 1, b = 2;

    int c = (num % 2) * a + ((num + 1) % 2) * b;

    printf("%d\n", c);

    return 0;
}
```

```c
#include <stdio.h>

int main(void) {
    for (int i = 1233456; i > 0; i /= 10) {
        printf("%d\n", i % 10);
    }

    return 0;
}
```

-   迴圈

```c
#include <stdio.h>

int main(void) {
    int num;

    while (scanf("%d", &num) == 1) {
        printf("%d\n", num);
    }

    return 0;
}
```

```c
int main(void) {
    for ( ; ; );

    return 0;
}
```

-   其他

```c
#include <stdio.h>

int main(void) {
    size_t size = sizeof(int);

    printf("%zu", size);

    return 0;
}
```
