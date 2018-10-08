题目三：统计所输入字符串中数字、字母、空格以及其他字符的个数
思路（C语言）：根据题目，要统计的数据有四类，这就可以定义四个变量来分别计入个数了
用if else语句来对四类数据进行分类，将要统计的字符串存入字符数组中，通过循环的方式对每一个数组元素进行判断，最终统计结果


代码如下：
#include<stdio.h>
#include<stdlib.h>
#pragma warning(disable:4996)//消除版本兼容问题
int main() 
{
	char a[20];
	int number = 0, letter = 0, space = 0, other = 0, i;
	printf("please input a sentence:\n");
	for (i = 0; i < 20; i++)
		scanf("%c",&a[i]);
	for(i=0;i<20;i++)
	{
		if (a[i] >= '0' && a[i] <= '9')
		{
			number ++;
		}
		else if(a[i]>='A'&&a[i]<='Z'||a[i]>='a'&&a[i]<='z')
		{
			letter ++;
		}
		else if (a[i] == 32)
		{
			space ++;
		}
		else
		{
			other ++;
		}
	}
	printf("number=%d\nletter=%d\nspace=%d\nother=%d\n",number,letter,space,other);
	system("pause");
	return 0;
}
