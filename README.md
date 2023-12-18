# 实验三 分支结构程序设计
## 实验目的
1.了解C语言表示逻辑量的方法。  
2.学会正确使用逻辑运算符和逻辑表达式。  
3.熟练掌握if语句和switch语句。  
4.熟悉分支结构程序设计。  
## 实验准备
1.复习关系、逻辑、条件运算和表达式。  
2.复习if语句的三种形式。  
3.复习if语句的嵌套。  
4.复习多分枝选择switch语句。  
5.源程序。  
## 实验步骤及内容 =
1.调试下列程序。  
```
#include<stdio.h>
int main() {
	int a, b, max, min;
	scanf_s("%d%d", &a, &b);
	if (a > b) {
		max = a; min = b;
	}
	else {
		min = a; max = b;
	}
	printf("max=%d,min=%d\n", max, min);
	return 0;
}
```
功能：实现了判断输入数字的大小。  
程序的另一种实现：
```
int main() {
	int a, b, max, min;
	scanf_s("%d%d", &a, &b);
	max = (a > b) ? a : b;
	min = (a < b) ? a : b;
	printf("max=%d,min=%d\n", max, min);
	return 0;
}
```
a问题：
```
#include<stdio.h>
int main() {
    int x,y;
    scanf("%d",&x);
    if (x < 1) {
        y = x;
    }
    else if (x >= 1 && x < 10) {
        y = 2 * x - 1;
    }
    else {
        y = 3 * x - 11;
    }
    printf("%d", y);
    return 0;
}
```
b问题：
```
#include<stdio.h>
int main() {
    int score;
    scanf_s("%d",&score);
    score = score / 10;
    switch (score) {
        case 9:
            printf("A");
            break;
        case 8:
            printf("B");
            break;
        case 7:
            printf("C");
            break;
        case 6:
            printf("D");
            break;
        default:
            printf("E");
            break;
    }
    return 0;
}
```
c问题：
```
#include <stdio.h>

int main() {
    int num, di = 0, tmp;

    scanf_s("%d", &num);

    tmp = num;
    while (tmp != 0) {
        tmp = tmp / 10;
        di++;
    }

    printf("%d位数.\n", di);

    tmp = num;
    while (tmp != 0) {
        printf("%d ", tmp % 10);
        tmp = tmp / 10;
    }
    printf("\n");

    tmp = num;
    while (tmp != 0) {
        printf("%d ", tmp % 10);
        tmp = tmp / 10;
    }
    printf("\n");

    int arr[4] = { 0 };
    tmp = num;
    for (int i = 0; i < 4 && tmp != 0; i++) {
        arr[i] = tmp % 10;
        tmp = tmp / 10;
    }

    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3 - i; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }

    for (int i = 0; i < 4; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    return 0;
}
```
## 实验报告

本次实验通过设计和编写分支结构程序，了解了分支结构的基本使用方法与理念思想。通过if-else语句或switch语句选择执行不同的分支，通过逻辑运算符和条件表达式根据不同的条件判断选择输出不同的结果。
