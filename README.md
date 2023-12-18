# 实验五 数组

## 实验目的
①掌握一维数组和二维数组的定义、赋值和输入输出的方法。   
②掌握字符数组和字符串函数的使用。   
③掌握与数组有关的算法（特别是排序算法）。   
## 实验准备
①复习数组的基本知识。   
②复习字符串数组的特点和常用的字符串处理函数。   
③源程序。   
## 实验步骤及内容

编写下列问题的源程序并上机调试运行。

1.用选择法对10个整数排序（10个整数用 scanf 函数输入）。
```
#include<stdio.h>

void a(int* a, int* b) {
	int temp = *a;
	*a = *b;
	*b = temp;
}

int main() {
	int x[10] = { 0 };
	for (int i = 0; i < 10; i++) {
		scanf_s("%d", &x[i]);
	}
	int len = sizeof(x) / sizeof(x[0]);
	for (int i = 0; i < len - 1; i++) {
		int min = i;
		for (int j = i + 1; j < len; j++) {
			if (x[j] < x[min]) {
				min = j;
			}
		}
		a(&x[min], &x[i]);
	}
	for (int i = 0; i < len; i++) {
		printf("%d ", x[i]);
	}
	return 0;
}
```
结果：   
![image](https://github.com/studyusssssing/report3/assets/152676097/1758f0ce-dad2-426c-9768-644d059765b1)

2.有15个数存放在一个数组中，输入一个数，要求用折半查找法找出该数是数组中第几个元素的值。如果该数不在数组中，则输出"无此数"。15个数用赋初值的方法在程序中给出。要找的数用 scanf 函数输入。
```
#include<stdio.h>
int main() {
    int a;
    scanf_s("%d", &a);
    int n[15] = { 0 };
    for (int i = 0; i < 15; i++) {
        scanf_s("%d", &n[i]);
    }
    int rig = 14, lef = 0;
    int prime = 1;
    while (lef <= rig) {
        int mid = (rig + lef) / 2;
        if (n[mid] > a) {
            rig = mid - 1;
        }
        else if (n[mid] < a) {
            lef = mid + 1;
        }
        else {
            printf("%d", mid);
            prime = 0;
            break;
        }
    }
    if (prime == 1) {
        printf("无此数");
    }
    return 0;
}
```
结果：![image](https://github.com/studyusssssing/report3/assets/152676097/e6bb4134-6d02-47f2-aaf5-b0fd05edb25c)

3.将两个字符串连接起来，不要用 strcat 函数。

```
#include<stdio.h>
int main()
{
    char str1[20]="Hoshi", str2[20]="zora";
    int i = 0, j = 0;

    while (str1[i] != '\0')
    {
        i++;
    }
    while (str2[j] != '\0')
    {
        str1[i++] = str2[j++];
    }
    str1[i] = '\0';
    printf("%s\n", str1);
    return 0;
}
```
结果：  
![image](https://github.com/studyusssssing/report3/assets/152676097/97ea21d9-20ba-445b-87cd-faf8fa57ac1a)

4.找出一个二维数组的"鞍点"，即该位置上的元素在该行上最大，在该列上最小。也可能没有鞍点。此二维数组可以设定如下，其中，数组元素的值用赋初值方法在程序中指定。
```
#include <stdio.h>
void findSaddlePoint(int arr[3][4]) {
    int x[3] = {0 };
    int y[4] = {0 };
    int i, j;

    for (i = 0; i < 3; ++i) {
        for (j = 0; j < 4; ++j) {
            if (arr[i][j] > arr[i][x[i]]) {
                x[i] = j;
            }
        }
    }

    for (j = 0; j < 4; ++j) {
        for (i = 0; i < 3; ++i) {
            if (arr[i][j] < arr[y[j]][j]) {
                y[j] = i;
            }
        }
    }

    for (i = 0; i < 3; ++i) {
        for (j = 0; j < 4; ++j) {
            if (x[i] == j && y[j] == i) {
                printf("(%d, %d): %d\n", i, j, arr[i][j]);
            }
        }
    }
}

int main() {
    int arr[3][4] = {
            {9,80,205,40},
            {90,-60,96,1},
            {210,-3,101,89}
    };

    findSaddlePoint(arr);

    return 0;
}
```
结果：  
![image](https://github.com/studyusssssing/report3/assets/152676097/60a7b7fc-7a52-4900-bb68-763c015f06b8)

## 实验结果
本次实验学习了数组的基本概念和使用方法，以及数组引用、访问、修改、初始化等操作。
