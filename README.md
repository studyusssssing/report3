# 2.7 实验七 指针
## (1)实验目的
①熟练掌握指针、地址、指针类型、void 指针空指针等概念。    
②熟练掌握指针变量的定义和初始化、指针的间接访问、指针的加减运算和指针表达式。    
③会使用数组的指针和指向数组的指针变量。    
④会使用字符串的指针和指向字符串的指针变量。
## (2)实验准备
①复习变量、变量的地址、指针变量的概念并且明确的区分这三个不同概念。    
②复习指针和数组的结合运用。    
③复习指针的其他理论知识。    
④源程序。
## (3)实验步骤及内容
①阅读程序,分析可能产生的结果,并在机器上运行。    
```
#include <stdio.h>
void main(){
int i,*p;
p=&i;
*p=5;
printf("%d\n",i);
printf("%d\n",*p);
printf("%d\n",p);
printf("%d\n",&i);
}
```
![image](https://github.com/studyusssssing/report3/assets/152676097/0ed3c87b-ce7e-4635-a172-774f73dacabe)

②用指针对n个整数进行排序，并将结果顺序输出。要求排序用一个函数实现，主函数只输人n个整数和输出已排序的n个整数。    
```
#include <stdio.h>

void bubbleSort(int *arr, int n);
int main() {
    int n;
    scanf("%d", &n);
    int arr[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    bubbleSort(arr, n);
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    return 0;
}

void bubbleSort(int *arr, int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

```
③编写一个函数alloc( n) ,用来在内存新开辟-一个连续的空间(n个字节)。再写一个函数free(p),将以地址p开始的各单元释放。主程序输人10个不等长的大写字符串，每输人一个字符串，应放在新申请的一片连续的空间。该字符串反序输出后，释放它所占用的空间。
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
char* alloc(int n);
void freeMemory(char *p);
int main() {
    char *str;
    int i, len;
    for (i = 0; i < 10; i++) {
        scanf("%ms", &str); // 使用 %ms 以动态分配内存保存字符串
        len = strlen(str);

        char *newStr = alloc(len + 1); // +1 用于存储字符串结束符 '\0'

        strcpy(newStr, str);

        printf("反序输出第 %d 个字符串: ", i + 1);
        for (int j = len - 1; j >= 0; j--) {
            printf("%c", newStr[j]);
        }
        printf("\n");

        freeMemory(newStr);

        free(str);
    }

    return 0;
}
char* alloc(int n) {
    return (char*)malloc(n);
}
void freeMemory(char *p) {
    free(p);
}
```

## (4)实验报告
变量的地址是指变量在内存中的位置。通过使用取地址运算符&，你可以获取变量的地址，例如&x表示变量x的地址。    
指针变量是一种特殊类型的变量，它存储的值是内存地址。指针变量用于存储其他变量的地址。通过指针，我们可以访问或修改存储在特定地址上的数据。
