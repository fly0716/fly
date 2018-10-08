题目二：计算1008！mod25的值
思路（C语言）：此题先求1008的阶乘对25求余，由于1008！数值太大，代码中要用到超长整数类型long long，不过我自己还真不知道1008!mod的最后结果！！
求1008！的阶乘分两个阶段，第一阶段是0和1的阶乘这个部分，还有就是2到1008的部分，后部分要用到循环语句

代码如下：
#include<stdio.h>
#include<stdlib.h>
#pragma warning(disable:4996)
#define LL long long//由于1008！太长，这里声明一个超长整型类型LL
int main() 
{
	LL x, y;//定义两个超长整型变量，x表示多少阶乘，y表示求模的数
	scanf("%lld %lld",&x,&y);
	if (x == 0 || x == 1)//0和1的阶乘值为1
	{
		printf("%lld\n",1%y); 
	}
	else
	{
		LL sum = 1;
		for (LL i = 2; i <= x; i++)
		{
			sum *= i;
		}
		printf("%lld\n",sum);
		sum %= y;
		printf("%lld\n", sum);
	}
	system("pause");
	return 0;
}

