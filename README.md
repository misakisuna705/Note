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
        + [換銅板](#換銅板)
        + [城堡](#城堡)
        + [皇后](#皇后)
        + [騎士](#騎士)
        + [前序](#前序)
        + [Binary Search](#binary-search)
        + [Merge Sort](#merge-sort)

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

|   概念   |             命名              |
| :------: | :---------------------------: |
|   變數   |          value / val          |
|   資料   |          data / dat           |
|   指標   |              ptr              |
|   陣列   |              arr              |
|   字串   |              str              |
| for 迴圈 |           i / j / k           |
|  前一個  |          pre / prev           |
|  這一個  |              cur              |
|  後一個  |          nxt / next           |
|   旗標   |             flag              |
|   參考   |             table             |
|   紀錄   |             mark              |
|    數    | num / n / size / len / length |
|   總數   |             total             |
|   剩餘   |            remain             |
|   索引   |          index / idx          |
|   計數   |          count / cnt          |
|   矩陣   |            matrix             |
|    列    |              row              |
|    行    |              col              |
|   創建   |           create();           |
|   設置   |             set()             |
|   取得   |             get()             |
|   排序   |            sort()             |
|   查找   |            find()             |
|   計算   |             cal()             |
|   字母   |              ch               |
|    頭    |             head              |
|    中    |              mid              |
|    尾    |             tail              |
|    左    |             left              |
|    右    |             right             |
|   最大   |              max              |
|   最小   |              min              |
|   緩衝   |              buf              |

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

#### 換銅板

```c
void change(int remain, int idx) {
    if (remain < 0 || idx >= n) {
        return;
    } else if (remain == 0) {
        show(n);
    } else {
        change(remain, idx + 1);

        ++num[idx];

        change(remain - table[idx], idx);

        --num[idx];
    }
}
```

#### 城堡

```c
void set_chess(int row) {
    if (row > N) {
        show();
    } else {
        for (int i = 1; i <= N; ++i) {
            if (valid(row, i)) {
                board[row][i] = 1;
                set_chess(row + 1);
                board[row][i] = 0;
            }
        }
    }
}
```

#### 皇后

```c
void set_chess(int row) {
    if (row == N) {
        show();
    } else {
        for (int i = 0; i < N; ++i) {
            if (valid(row, i)) {
                board[row] = i;
                set_chess(row + 1);
            }
        }
    }
}
```

#### 騎士

```c
void set_chess(int row, int col, int num) {
    if (num == N * N + 1) {
        show();
    } else {
        if (valid(row, col)) {
            board[row][col] = num;

            set_chess(row + 2, col + 1, num + 1);
            set_chess(row + 2, col - 1, num + 1);
            set_chess(row - 2, col + 1, num + 1);
            set_chess(row - 2, col - 1, num + 1);
            set_chess(row + 1, col + 2, num + 1);
            set_chess(row + 1, col - 2, num + 1);
            set_chess(row - 1, col + 2, num + 1);
            set_chess(row - 1, col - 2, num + 1);

            board[row][col] = 0;
        }
    }
}
```

#### 前序

```c
int cal(void) {
    char ch = getchar();

    if (isdigit(ch)) {
        int ans;

        ungetc(ch, stdin);
        scanf("%d", &ans);

        return ans;
    } else if (ch == '+') {
        int a = cal();
        int b = cal();

        return a + b;
    } else if (ch == '-') {
        int a = cal();
        int b = cal();

        return a - b;
    } else if (ch == '*') {
        int a = cal();
        int b = cal();

        return a * b;
    } else {
        return cal();
    }
}
```

#### Binary Search

```c
void find(int num, int head, int tail) {
    int mid = (head + tail) / 2;

    if (head > tail) {
        printf("NULL");
    } else if (dat[mid] == num) {
        printf("%d\n", mid);
    } else {
        if (dat[mid] > num) {
            find(num, head, mid - 1);
        } else {
            find(num, mid + 1, tail);
        }
    }
}
```

#### Merge Sort

```c
void sort(int left, int right) {
    if (left > right) {
        return;
    } else {
        int mid = (left + right) / 2;

        sort(left, mid);
        sort(mid + 1, right);

        merge(arr + left, mid - left + 1, arr + mid + 1, right - mid);

        for (int i = 0; i < right - left + 1; i++) {
            arr[left + i] = buf[i];
        }
    }
}

void merge(int arr_1[], int len_1, int arr_2[], int len_2) {
    int i = 0, j = 0, k = 0;

    while (i < len_1 && j < len_2) {
        if (arr_1[i] < arr_2[j]) {
            buf[k] = arr_1[i];

            i++;
            k++;
        } else {
            buf[k] = arr_2[j];

            j++;
            k++;
        }
    }

    while (i < len_1) {
        buf[k] = arr_1[i];

        i++;
        k++;
    }

    while (j < len_2) {
        buf[k] = arr_2[j];

        j++;
        k++;
    }
}
```
