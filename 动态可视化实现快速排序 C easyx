# 动态可视化实现快速排序
————————————————————————————————————

```C

	#include<stdio.h>
	#include"graphics.h"
	#include"conio.h"
	#include<stdlib.h>
	#include<string.h>
	int k = 1;
	int QuickSort(int r[], int low, int high,int n,int k)
	{
		int i, j;
		if (low < high)
		{
			i = low;
			j = high;
			r[0] = r[i];
			do
			{
				while (r[j] > r[0] && i < j)
				{
					if (k == 1)
					{
						circle(85 + 30 * j, 30 * k, 10);
					}
					else 
						circle(85 + 30 * j, 60 + 30 * k, 10);
					 j--;Sleep(500);

				}
				if(r[j] < r[0])  circle(85 + 30 * j , 30 * k, 10);
				if(i<j)
				{
					r[i] = r[j]; i++; 
				}
				while (r[i] < r[0] && i < j)
				{
					if (k == 1)
					{
						circle(85 + 30 * i, 30 * k, 10);
					}
					else 
						circle(85 + 30 * i, 60 + 30 * k, 10);
					 i++; Sleep(500); 
				}
				if(r[i] > r[0])  circle(85 + 30 * i , 30 * k, 10);
				if(i < j)
				{
					r[j] = r[i]; j--;
				}
				Sleep(500);
			} while (i != j);
			r[i] = r[0]; 
			printf("%d", r[0]);
			printf("第%d次排序：", k); k++;
			for (int m = 1; m < n+1; m++)
				printf(" %2d ", r[m]);
			printf("\n");
			outtextxy(20, 60+30*k, "next：" );
			outtextxy(65, 90, "分界值");
			Sleep(1000);
			char str[5];
			sprintf_s(str, 5, "%d", r[0]);
			outtextxy(80 , 60 + 30 * k, str);
			for (int h = 1; h < n + 1; h++)
			{
				char strRes[5];
				sprintf_s(strRes, 5, "%d", r[h]);
				outtextxy(80 + 30 * h, 60 + 30*k, strRes);
			}
			k = QuickSort(r, low, i - 1,n,k);
			k = QuickSort(r, i + 1, high,n,k);
		}return k;

	}
	int main()
	{
		int n,k=1;
		int r[50];
		printf("请输入数组的大小：");
		scanf("%d", &n);
		r[0] = 0;
		for(int i =1; i < n+1;i++)
			scanf("%d", &r[i]);
		initgraph(640, 480);
		outtextxy(20, 30, "初始化：");
		for (int i = 1; i < n + 1; i++)
		{
			char strRes[5]; 
			sprintf_s(strRes, 5, "%d", r[i]);
			outtextxy(80+30*i, 30, strRes);
		}
		k = QuickSort(r, 1, n ,n,k);
		for (int i = 1; i < n+1; i++)
			printf("%d ", r[i]);
		printf("\n");
		system("pause");
		closegraph();
		system("pause");
		return 0;
	}
```
