题目：求工作室群号的最大质因数
思路（C语言）：根据题意，就是求一个数的最大质因数。
一个数模上另一个数，如果结果为0，后面那个数就是第一个数的质因数，但我们求得是最大质因数，所以，用两数模的结果再一次进行相同的步骤且后面的数每循环一次就+1，
直到两数模的结果不为0，循环结束，最终后面的那个数就是最大质因数


代码如下：
#include<stdio.h>
#include<stdlib.h>
#pragma warning(disable:4996)
int main() 
{
	int num, y, i = 2;
	printf("please input the number of gongzuoshi:\n");
	scanf("%d",&num);
	while (num > 2)
	{
		if (num%i == 0)
		{
			y = i;
			num /= i;
		}
		else
			i++;
	}
	printf("%d\n",y);
	system("pause");
	return 0;
}
