# vs2013-2-1
#define _CRT_SECURE_NO_WARNINGS 1

//int main()
//{
//	//未初始化的指针变量
//	int* p;//局部变量不初始化，里边默认放的是一个随机值
//	*p = 20;
//
//	return 0;
//}
//
//数组越界导致的野指针问题
//int main()
//{
//	int a[10] = { 0 };
//	int i = 0;
//	int* p = a;
//	for (i = 0; i <= 12; i++)
//	{
//		//*p = i;
//		//p++;
//		*p++ = i;
//	}
//
//	return 0;
//}
//
//#include<stdio.h>
//
//int* test()
//{
//	/*int a = 10;
//	return &a;*/
//	int arr[10] = { 0 };
//	return arr;
//}
//int main()
//{
//	int* p = test();
//	printf("%d\n", *p);
//
//	return 0;
//}
//
//如何规避野指针
//1.指针初始化
//int main()
//{
//	int a = 10;
//	int*pa = &a;//初始化
//	int* p = NULL;//NULL-用来初始化指针的，给指针赋值
//
//}
//2.小心指针越界
//3.指针指向空间置为NULL
//int main()
//{
//	int a = 10;
//	int *pa = &a;
//	*pa = 20;
//	//
//	pa = NULL;
//}
//4.指针使用之前检查有效性
//int main()
//{
//	int a = 10;
//	int *pa = &a;
//	*pa = 20;
//	pa = NULL;
//	//*pa = 10;
//	if (pa != NULL)
//	{
//
//	}
//}
#include<stdio.h>
//int main()
//{
//	int arr[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
//	int i = 0;
//	int sz = sizeof(arr) / sizeof(arr[0]);
//	int* p = arr;
//	//for (i = 0; i < sz; i++)
//	//{
//	//	printf("%d ", *p);
//	//	p++;
//	//	//p = p + 1;
//	//}
//	for (i = 0; i < 5; i++)
//	{
//		printf("%d ", *p);
//		p+=2;
//		//p = p + 1;
//	}
//	return 0;
//}

//int main()
//{
//	int arr[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
//	int i = 0;
//	int sz = sizeof(arr) / sizeof(arr[0]);
//	int* p = &arr[9];
//	//for (i = 0; i < sz; i++)
//	//{
//	//	printf("%d ", *p);
//	//	p++;
//	//	//p = p + 1;
//	//}
//	for (i = 0; i < 5; i++)
//	{
//		printf("%d ", *p);
//		p -= 2;
//		//p = p + 1;
//	}
//	return 0;
//}

//#define N_VALUES 5
//float values[N_VALUES];
//float *vp;
////指针+-整数：指针的关系运算
//for (vp = &values[0]; vp < &values[N_VALUES];)
//{
//	*vp++ = 0;
//}
//指针-指针=元素个数
//int my_strlen(char *s)
//{
//	char *p = s;
//	while (*p != '\0')
//		p++;
//	return p - s;
//}
//int main()
//{
//	int arr[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
//	printf("%d\n", &arr[9] - &arr[0]);//9
//	return 0;
//}
//int main()
//{
//	int arr[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
//	printf("%d\n", &arr[0] - &arr[9]);//-9
//	return 0;
//}
//
//int main()
//{
//	char ch[5] = { 0 };
//	int arr[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
//	printf("%d\n", &arr[9] - &arr[0]);//
//	printf("%d\n", &arr[9] - &ch[0]);//不能这么写error
//	return 0;
//}
//int my_strlen(char* str)
//{
//	char* start = str;
//	char* end = str;
//	while (*end != '\0')
//	{
//		end++;
//	}
//	return end - start;//
//}
//int main()
//{
//	//strlen - 求字符串长度
//	//递归 - 模拟实现了strlen - 计数器的方式1，递归的方式2
//	char arr[] = "bit";
//	int len=my_strlen(arr);
//	printf("%d\n", len);
//	return 0;
//
//}

//int main()
//{
//	int arr[10] = { 0 };
//	printf("%p\n", arr);//地址-首元素的地址
//	printf("%p\n", arr+1);
//
//	printf("%p\n", &arr[0]);
//	printf("%p\n", &arr[0]+1);
//
//	//1.&arr - -&数组名 - 数组名不是首元素的地址 - 数组名表示整个数组 - &数组名 取出的是整个数组的地址
//	//2.sizeof(arr) - sizeof(数组名） - 数组名表示的整个数组 - sizeof（数组名）计算的是整个数组的大小
//	printf("%p\n", &arr);//
//	printf("%p\n", &arr+1);
//	return 0;
//}
//int main()
//{
//	int arr[10] = { 0 };
//	int* p = arr;
//	int i = 0;
//	for (i = 0; i < 10; i++)
//	{
//		*(p + i) = i;
//	}
//	for (i = 0; i < 10; i++)
//	{
//		printf("%d\n", *(p+i));
//	}
//	/*for (i = 0; i < 10; i++)
//	{
//		printf("%p  =====   %p\n", p + i; &arr[i]);
//	}*/
//	return 0;
//}

//int main()
//{
//	int a = 10;
//	int * pa = &a;
//	int* * ppa = &pa;//ppa就是一个二级指针
//	//int** * pppa = &ppa;
//	**ppa = 20;
//	printf("%d\n", **ppa);//20
//	return 0;
//}

//好孩子 - 孩子
//指针数组 - 数组 - 存放只指针的数组
//数组指针 - 指针
int main()
{
	int a = 10;
	int b = 20;
	int c = 30;
	//int* pa = &a;
	//int* pb = &b;
	//int* pc = &c;
	//整形数组 - 存放整形
	//字符数组 - 存放字符
	//指针数组 - 存放指针
	//int arr[10];
	int* arr2[3] = { &a, &b, &c };//指针数组
	int i = 0;
	for (i = 0; i < 3; i++)
	{
		printf("%d\n",*(arr2[i]));//10 20 30
	}
	return 0;
}
