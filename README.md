# 蛮力法解决凸包问题-easyx-
--------------------------
c vs2017 easyx

```C
#include <graphics.h>
#include <conio.h>
#define N 50

struct Point
{
	double x;
	double y;
	int flag;
}point[N];

void ConvexHull(int n)
{
	double a, b, c;
	int sign1, sign2, k;
	for (int i = 0; i < n; ++i)
	{
		for (int j = i + 1; j < n; ++j)
		{
			a = point[j].y - point[i].y;
			b = point[i].x - point[j].x;
			c = (point[i].x * point[j].y) - (point[i].y * point[j].x);
			sign1 = 0;
			sign2 = 0;
			for (k = 0; k < n; ++k)                                                                     
			{
				if ((k == j) || (k == i)) continue;
				else {
					if ((a * point[k].x + b * point[k].y) == c)
					{
						++sign1; ++sign2;
					}
					if ((a * point[k].x + b * point[k].y) > c)
						++sign1;
					if ((a * point[k].x + b * point[k].y) < c)
						++sign2;
				}
			}
			if ((sign1 == (n - 2)) || (sign2 == (n - 2)))
			{
				point[i].flag = 1;
				point[j].flag = 1;
				setlinecolor(RED);
				line(point[i].x, point[i].y, point[j].x, point[j].y);
			}
		}
	}
}

int main()
{

	initgraph(640, 480);
	int i = 0;
	MOUSEMSG m;
	
	while (true)
	{
		m = GetMouseMsg();

		switch (m.uMsg) 
		{

		case WM_LBUTTONDOWN: 
			
			circle(m.x, m.y, 1);
			point[i].x = m.x;
			point[i].y = m.y;
			point[i].flag = 0;
			i++;
			break;

		case WM_RBUTTONUP:
			ConvexHull(i);
			break;
		}
	}

	_getch();
	closegraph(); 
	return 0;
}
```
