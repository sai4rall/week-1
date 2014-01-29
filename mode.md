/* To find the number most repeated */
#include<stdio.h>
#include<stdlib.h>
#include<conio.h>
int main()
{
    int n,r,m;
    scanf("%d",&n);
    int *arr=(int *)malloc(n*sizeof(int));
    int i;
    int max=0;
    for(i=0;i<n;i++)
    {
        scanf("%d",&arr[i]);
        if(arr[max]<arr[i])
            max=i;
    }
   int *b=(int *)malloc((arr[max]+1)*sizeof(int));
   for(i=0;i<arr[max]+1;i++)
        b[i]=0;
    for(i=0;i<n;i++)
      b[arr[i]]++;
	r=b[0];
	for(i=1;i<arr[max]+1;i++)
    {
        if(r<b[i])
		{
			r=b[i];
			m=i;
		}
	}
    
	printf("%d is repeated %d times",m,r);
	getch();
  return 0;
	
}

