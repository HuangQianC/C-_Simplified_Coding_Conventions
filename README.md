# C++ 简明编码习惯

## 1. 运算符与空格
- 运算符左右各加一个空格，函数参数与参数之间加一个空格，`if`、`while` 等条件之后加一个空格，函数名与左花括号 `{` 之间有一个空格：

```cpp
int sum = a + b; // 运算符左右加空格
void func(int x, int y) { // 函数参数之间加空格
    // 逻辑
}
if (x > y) { // if 条件后加空格
    // 逻辑
}
void myFunction() { // 函数名与左花括号之间加空格
    // 逻辑
}
