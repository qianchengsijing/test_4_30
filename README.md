# test_4_30
#include <stdio.h>
#include <assert.h>
//栈在递归中的应用
void func2(int x)
{
	int m,n;
	m = x+1;
	n = x+2;
}
void func1(int a,int b)
{
	int x = a+b;
	func2(x);
	x = x+10086;
}
void main()
{
	int a=1,b=2,c=3;
	func1(a,b);
	c = a+b;
}
//递归求解阶乘
int factorial(int n)
{
	if(n == 0 || n == 1)
		return 1;
	else
		return n*factorial(n-1);
}
int main()
{
	int x = factorial(10);
	printf("x = %d\n",x);
	return 0;
}
//递归求解斐波那契数
int Fib(int n)
{
	if(n == 0)
		return 0;
	else if(n == 1)
		return 1;
	else
		return Fib(n-1) + Fib(n-2);
}
int main()
{
	int x = Fib(4);
	printf("x = %d\n",x);
	return 0;
}
//设计一个程序判断当前机器字节序存储模式
int main()
{
	int a = 1;
	char *p = (char*) &a;
	if(*p == 1)
		printf("大端\n");
	else
		printf("小端\n");
}
//函数实现
int check_sys()
{
	int a = 1;
	char *p = (char*) &a;
	if(*p == 1)
		return 1;
	else
		return 0;
}
//优化
int check_sys()
{
	int a = 1;
	char *p = (char*) &a;
	return *p;
}
int check_sys()
{
	int a = 1;
	return *(char*)&a;
}
int main()
{
	int ret = check_sys();
	if(ret == 1)
		printf("大端\n");
	else
		printf("小端\n");
}
//模拟strlen函数
int my_strlen(const char* str)
{
	int count = 0;
	assert(str != NULL);
	while(*str != '\0')
	{
		count++;
		str++;
	}
	return count;
}
int main()
{
	char arr[]="abcdef";
	int len = my_strlen(arr);
	printf("len = %d\n",len);
	return 0;
}
//编写strcpy函数
void my_strcpy(char* dest,char* src)
{
	*dest = *src;
	while(*src != '\0')
	{
		dest++;
		src++;
		*dest = *src;
	}
}
//优化
char* my_strcpy(char* dest,const char* src)
{
	char* ret = dest;
	assert(src != NULL);
	assert(dest != NULL);
	while(*dest++ = *src++)
	{
		;
	}
	return ret;
}
int main()
{
	char arr1[]="##############";
	char arr2[]="bit";
	my_strcpy(arr1,arr2);
	printf("%s\n",arr1);
	printf("%s\n",my_strcpy(arr1,arr2));
	return 0;
}
