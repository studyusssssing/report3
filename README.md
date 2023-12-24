# 实验六 函数
## 实验目的
①掌握定义函数的方法。	  
②掌握函数实参与形参的对应关系，以及“值传递”的方式。	  
③掌握函数的嵌套调用和递归调用的方法。	  
④掌握全局变量、局部变量、动态变量和静态变量的概念和使用方法。	  
⑤理解和掌握多模块的程序设计与调试的方法。
## 实验准备
①复习函数调用的基本理论知识。   
②复习函数的嵌套调用和递归调用的方法。   
③复习全局变量、局部变量;静态变量、动态变量;外部变量等概念和具体使用。   
④源程序。
## 实验步骤及内容
①写一函数,求一个字符串的长度。   
要求:      
●本部分习题要求全部用指针完成。   
●在main函数中输人字符串，并输出其长度。   
●本题不能使用strlen()函数。
```
#include <stdio.h>
int stringLength(const char *str) {
    const char *ptr = str;
    while (*ptr != '\0') {
        ptr++;
    }
    return ptr - str;
}
int main() {
    char inputString[100];
    scanf("%s", inputString);
    int length = stringLength(inputString);
    printf("%d", length);
    return 0;
}
```
②编写一个丽数,将数组中n个数按反序存放。   
要求:   
●在主函数中输入10个数，并输出排好序的数。   
●编写函数invert( )将10个数按反序存放。   
```
#include <stdio.h>

void invert(int arr[], int n) {
    int temp;
    for (int i = 0; i < n / 2; ++i) {
        temp = arr[i];
        arr[i] = arr[n - 1 - i];
        arr[n - 1 - i] = temp;
    }
}

int main() {
    int n = 10; 
    int numbers[n];
    for (int i = 0; i < n; ++i) {
        scanf("%d", &numbers[i]);
    }
    invert(numbers, n);
    for (int i = 0; i < n; ++i) {
        printf("%d ", numbers[i]);
    }
    return 0;
}
```
③设计一个函数，调用它时，每次实现不同的功能:   
●求两个数之和;   
●求两个数之差;   
●求两个数之积。   
要求:    
●在主函数中输入2个数a,b,并输出a,b的和、差和乘积。   
●分别编写函数add()、sub( )、mul( )计算两个数的和、差、积。   
●编写函数process( )，分别调用函数add()、sub()、mul( )。   
```
#include <stdio.h>

// 函数声明
int main() {
    int a, b;
    scanf("%d %d", &a, &b);
    int choice;
    printf("1. 求和\n2. 求差\n3. 求积\n");
    scanf("%d", &choice);
    process(a, b, choice);
    return 0;
}

int add(int a, int b) {
    return a + b;
}

int sub(int a, int b) {
    return a - b;
}

int mul(int a, int b) {
    return a * b;
}

void process(int a, int b, int choice) {
    switch (choice) {
        case 1:
            printf("%d\n", add(a, b));
            break;
        case 2:
            printf("%d\n", sub(a, b));
            break;
        case 3:
            printf("%d\n", mul(a, b));
            break;
    }
}
```
## 实验结果
本次实验学习了定义函数的方法，掌握函数实参与形参的对应关系，以及“值传递”的方式，嵌套调用和递归调用的方法，全局变量、局部变量、动态变量和静态变量的概念和使用方法。理解了多模块的程序设计与调试的方法。
