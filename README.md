# C / Cpp

<!-- vim-markdown-toc GFM -->

* [Coding Style](#coding-style)
    - [global 命名需完整，local 命名需簡潔](#global-命名需完整local-命名需簡潔)
    - [enum / macro / constant 使用全大寫](#enum--macro--constant-使用全大寫)
        + [enum](#enum)
        + [macro](#macro)
        + [constant](#constant)

<!-- vim-markdown-toc -->

## Coding Style

### global 命名需完整，local 命名需簡潔

|  global   |      local      |
| :-------: | :-------------: |
|   class   | member function |
| structure | member variable |
| function  |                 |
|   enum    |                 |
|   macro   |                 |
| variable  |                 |

### enum / macro / constant 使用全大寫

#### enum

```cpp
enum {
    MAIN_SCENE,
    PLAY_SCENE
};
```

#### macro

```cpp
#define MAX 1024
```

#### constant

```cpp
const int NUM;
```
