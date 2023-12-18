# 实验四 循环结构程序设计
## 实验目的
①熟悉用 while语句，do while语句和for语句实现循环的方法。    
②掌握在程序设计中用循环的方法实现各种算法（如穷举、迭代、递推等）。    
③掌握continue语句和break语句的使用。    
④熟练掌握循环结构的嵌套。    
⑤练习调试与修改程序。	
## 实验准备  
①复习 while 语句， do - while 语句和 for 语句的特点和适用条件。  
②复习 continue 语句和 break 语句的区别。  
③源程序。  
## 实验目的及内容
1.以下程序是用来计算 S =1+2+3+…+10，请更正下列程序的错误，并上机调试。
```
#include<stdio.h>
int main() {
	int i = 1,sum=0;
	while (i < 10) {
		sum += i;
		++i;
	}
	printf("sum=%d\n", sum);
	return 0;
}
```
2.
```c
#include<stdio.h>
int main() {
	int i = 1,sum=0;
	do{
		sum += i;
		++i;
	} while (i < 10);
	printf("sum=%d\n", sum);
	return 0;
}
```
3.
```
#include<stdio.h>
int main() {
	int i, sum = 0;
	for (i = 1; i < 10; i++) {
		sum += i;
	}
	printf("sum=%d\n", sum);
	return 0;
}
```
4.
输入并运行下面的程序，观察程序运行的结果
```
#include<stdio.h>
int main() {
	int n;
	while (1) {
		printf("Enter a number:");
		scanf_s("%d", &n);
		if (n % 2 == 1) {
			printf("I said");
			continue;
		}
		break;
	}
	printf("Thanks.I needed that!");
	return 0;
}
```
结果：![image](https://github.com/studyusssssing/report3/assets/152676097/78f23b6e-45cf-471c-bb35-8bee39b11f3f)
## 实验报告
本次实验学习了循环结构的基本概念和使用方法，学会了控制循环条件以达成程序目的。
