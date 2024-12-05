# C++ 简明编码习惯

## 1. 运算符左右各加一个空格，函数参数与参数之间加一个空格，if、while等条件之后加一个空格，函数名与左花括号'{'之间有一个空格；

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
```

## 2. 头文件包含的顺序： 本文件名.h【是指当前源文件（.cpp 文件）对应的头文件】、系统头文件、第三方库头文件、当前项目头文件；

```cpp
#include "MyHeader.h"  // 本文件头文件
#include <iostream>  // 系统头文件
#include <vector>  // 第三方库头文件
#include "ProjectHeader.h"  // 当前项目头文件
```

## 3. 类如果不被继承尽量使用 final 关键字修饰，改写父类的子类方法尽量使用 override 修饰；

## 4. 一个类如果定义了析构函数，则应该也尽量定义拷贝构造函数和赋值拷贝构造函数，C++11之后移动拷贝构造函数和赋值移动拷贝函数，如果不支持某个类型的拷贝，应该尽量使用 =delete 删掉，如果使用默认实现使用 =default 修饰。

## 5. 能用 const 尽量使用 const；

## 6. .cpp 文件中的函数实现和 .h 中定义的顺序应该尽量一致，功能相同的函数应该放在一起。

## 7. 尽量使用 RAII 惯用法，让资源自动分配和释放；即，在构造函数分配资源，在析构函数释放资源。

```cpp
class MyClass {
public:
    MyClass() {
        // 分配资源
    }
    ~MyClass() {
        // 释放资源
    }
};
```

## 8. 类的成员变量基本数据类型放在前面，复杂数据类型放在后面；

## 9. 类的成员变量如果不需要动态创建，尽量不要 new；函数中优先使用栈对象而不是堆对象；

## 10. 如果 if...else... 结构中的一个分支较短且简单，可以使用 return 提前结束，避免不必要的嵌套，使代码更加清晰和简洁。

```cpp
void process(int x, int y) {
    if (x <= y) {
        std::cout << "Nothing to do!" << std::endl;
        return;  // 提前结束短分支
    }
    
    // 长逻辑
    std::cout << "Processing complex branch..." << std::endl;
    // 更复杂的代码
}
```

## 11. 类的成员变量建议使用 m_ 或 _ 风格，函数参数不要使用该风格，大小写应该保持一致；

```cpp
class MyClass { // 使用 m_ 风格
public:
    int m_value;  // 成员变量使用 m_ 风格
    void setValue(int value) {  // 函数参数不使用 m_ 风格
        m_value = value;
    }
};

class MyClass { // 使用 _ 风格
public:
    int _value;  // 成员变量使用 _ 风格
    void setValue(int value) {  // 函数参数不使用 _ 风格
        _value = value;
    }
};
```

## 12. 类的 public、protected、private 方法和变量不要混在一起，建议分开写；

## 更多的编码风格可以看《Google C++ Styles》:
[Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)




