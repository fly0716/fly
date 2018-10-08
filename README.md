题目一、冒泡排序
思路：题目的意思是使数字一个个的往上浮，想气泡一样，重的气泡往下沉，这里更大的数字排在后面
假设有n个数需要进行大小排序，从前往后，第一个数与第二个数字进行比较大小，谁大，谁放后面，n个数字需要比较n-1趟，每一趟都需要比较n-1-（当前第几个数的位置，即当前数的数组下标），
最后得到从小到大排列的一组数据

代码如下：
#include<stdio.h>
#include<stdlib.h>
#pragma warning(disable:4996)
int main() 
{
	int a[10];
	int i, j, t;
	printf("please input 10 numbers:\n");//对10个数用冒泡法进行排序
	for (i = 0; i < 10; i++)//用循环语句输入10个数
		scanf("%d", &a[i]);
	printf("\n");
	for (j = 0; j < 9; j++)//10个数进行9轮大小比较
	{
		for (i = 0; i < 9 - j; i++)//每一轮进行9-j次大小比较
		{
			if (a[i] > a[i + 1])//相邻两个数进行比较，满足条件则两数进行位置交换
			{
				t = a[i];
				a[i] = a[i + 1];
				a[i + 1] = t;
			}
		}
	}
	printf("the last result:\n");
	for (i = 0; i < 10; i++)
		printf("%d ",a[i]);
	printf("\n");
	system("pause");
	return 0;
}
