题目四：实现substring，返回子串
思路（C语言）：据我的理解，根据题意，需要我从一个字符串中截取其中的一部分当做子串进行返回，最终输出结果
这里，我们可以设置两个字符数组，一个主串，一个子串，将从主串上截取的部分存入子串数组中，而要完成截取任务，要定义两个变量作为主串截取部分一头一尾的数组下标数字
这样就能通过键盘的输入来控制需要截取的部分


代码如下：
#include<stdio.h>
#include<stdlib.h>
#pragma warning(disable:4996)
void substring(char *,char *,int ,int);
int main()
{
	int i,x,y,j;
	char S[20], T[10];
	for (i = 0; i < 20; i++)
		scanf("%c",&S[i]);
	printf("please input two number for x and y:\n");//设置需在主串中截取的位置始末
	scanf("%d%d",&x,&y);
	substring(S,T,x,y);
	for (j = 0; j < y - x; j++)
		printf("%c",T[j]);
	printf("\n");
	system("pause");
	return 0;
}
void substring(char *S, char *T, int head, int end)
{
	int i;
	//将所需在主串中截取的部分存放在子串中
	for (i = 0; i < end; i++)
	{
		T[i] = S[head++];
	}
}
