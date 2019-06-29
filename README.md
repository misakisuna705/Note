# C / Cpp

<!-- vim-markdown-toc GFM -->

* [Coding Style](#coding-style)
    - [命名](#命名)
        + [內容](#內容)
        + [大小寫](#大小寫)
        + [常用命名](#常用命名)
    - [排版](#排版)
    - [註解](#註解)
* [idiom](#idiom)
    - [輸入輸出](#輸入輸出)
        + [空格補 0](#空格補-0)
        + [自訂格式符](#自訂格式符)
        + [忽略格式符](#忽略格式符)
        + [連續輸入](#連續輸入)
    - [迴圈](#迴圈)
        + [++i 比 i++ 好](#i-比-i-好)
        + [無窮迴圈](#無窮迴圈)
    - [遞迴](#遞迴)
    - [其他](#其他)
        + [sizeof 型態](#sizeof-型態)
        + [奇偶選擇](#奇偶選擇)
        + [取位數](#取位數)
        + [gcd](#gcd)
        + [Fibonacci](#fibonacci)
        + [快速冪](#快速冪)
        + [Tower of Honoi](#tower-of-honoi)

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
|   數量   |  size / n   |
| for 迴圈 |  i / j / k  |
|  前一個  | pre / prev  |
|  這一個  |     cur     |
|  後一個  | nxt / next  |

### 排版

### 註解

|    段落     |  單行  |
| :---------: | :----: |
| /\* ??? \*/ | // ??? |

## idiom

### 輸入輸出

#### 空格補 0

```c
#include <stdio.h>

int main(void) {
    printf("%05d\n", 999);

    return 0;
}
```

#### 自訂格式符

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

#### 忽略格式符

```c
#include <stdio.h>

int main(void) {
    int num;

    scanf("%*d %*d %d", &num);

    printf("%d\n", num);

    return 0;
}
```

#### 連續輸入

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
#include <stdio.h>

int main(void) {
    int num;

    while (scanf("%d", &num) != EOF) {
        printf("%d\n", num);
    }

    return 0;
}
```

```c
#include <stdio.h>

int main(void) {
    int ch;

    while ((ch = getchar()) != EOF) {
        //
    }

    return 0;
}
```

```c
#include <stdio.h>

int main(void) {
    char ch;

    while ((ch = getchar()) != '\n') {
        putchar(ch);

        getchar();
    }

    return 0;
}
```

### 迴圈

#### ++i 比 i++ 好

#### 無窮迴圈

```c
int main(void) {
    for ( ; ; );

    return 0;
}
```

### 遞迴

```c
void f(int n) {
    if (n == 0) {
        return;
    } else {
        f(n--);
        //
    }
}
```

```c
void f(int n) {
    if (n == 0) {
        return;
    } else {
        //
        f(n--);
    }
}
```

### 其他

#### sizeof 型態

```c
#include <stdio.h>

int main(void) {
    size_t size = sizeof(int);

    printf("%zu", size);

    return 0;
}
```

#### 奇偶選擇

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

#### 取位數

```c
#include <stdio.h>

int main(void) {
    for (int i = 1233456; i > 0; i /= 10) {
        printf("%d\n", i % 10);
    }

    return 0;
}
```

```c
#include <stdio.h>

void bin(int i) {
    if (i == 1) {
        printf("%d", i % 2);
    } else {
        bin(i / 2);
    }
}
```

#### gcd

```c
#include <stdio.h>

int main(void) {
    int a, b;
    scanf("%d %d", &a, &b);

    while(a && b) {
        if (a > b) {
            a = a % b;
        } else {
            b = b % a;
        }
    }

    if (a) {
        printf("%d\n", a);
    } else {
        printf("%d\n", b);
    }

    return 0;
}
```

```c
int gcd(int a, int b) {
    if (b == 0) {
        return a;
    } else {
        return gcd(b, a % b);
    }
}
```

#### Fibonacci

```c
#include <stdio.h>

int main(void) {
    int n;
    scanf("%d", &n);

    int fib[100] = {0, 1, 1};

    for(int i = 3; i <= n; ++i) {
        fib[i] = fib[i-1] + fib[i-2];
    }

    printf("%d\n", fib[n]);

    return 0;
}
```

```c
int fib(int i) {
    if(i == 1 || i == 2) {
        return 1;
    } else {
        return fib(i - 1) + fib(i - 2);
    }
}
```

```c
int table[100];

int fib(int i) {
    if (i == 1 || i == 2) {
        return 1;
    } else {
        if (table[i]) {
            return table[i];
        } else {
            table[i] = fib(i - 1) + fib(i - 2);

            return table[i];
        }
    }
}
```

#### 快速冪

```c
int power(int a, int n) {
    if (n == 1) {
        return a;
    } else {
        int sqrt = power(a,n/2);

        if (n % 2 == 0) {
            return sqrt * sqrt;
        } else {
            return a * sqrt * sqrt;
        }
    }
}
```

#### Tower of Honoi

```c
#include <stdio.h>

void hanoi(int a, int b, int c, int n) {
    if (n == 0) {
        return ;
    } else {
        hanoi(a, c, b, n - 1);
        printf("%d %d %d\n", n, a, b);
        hanoi(c, b, a, n - 1);
    }
}
```
