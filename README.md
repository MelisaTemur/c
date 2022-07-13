# c
STRUCTURES WITH MATHS IN C. 
#include<stdio.h>
#include<math.h>

struct point3D {
	int x;
	int y;
	int z;
}p[4];

int main(void)
{

	int i ;
	int j ;

	float value = 0;
	float min = -1;

	int p1 = 0;
	int p2 = 0;


	for (i = 0; i <= sizeof p / sizeof p[0]; i++)
	{
		printf("enter %d.point (x,y,z) : ", i + 1);
		scanf("%d ,%d ,%d", &p[i].x, &p[i].y, &p[i].z);
	
	}
	for (i = 0; i <= sizeof p / sizeof p[0]; i++)
	{
		for (j = 0; j <= sizeof p / sizeof p[0]; j++)
		{
			if (i == j)
				continue;

			value = abs(sqrt(pow((p[i].x - p[j].x), 2) + pow((p[i].y - p[j].y), 2) + pow((p[i].z - p[j].z), 2)));
			if (min == -1)
				min = value;
			else
			{
				if (min > value)
				{
					min = value;
					p1 = i + 1;
					p2 = j + 1;
				}
			}
		}

	}
	printf("Closest points are Point : -%d and Point -%d,Distance Between them = %.2f", p1, p2, min);

	return 0;
}
