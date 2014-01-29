/* To find the median */
#include<stdio.h>
#include<conio.h>
#include<stdlib.h>
 
void merge(int [], int, int [], int, int []);
 
int main() {
  int *a,*b, m, n, c, *sorted,k;
  float r;
  scanf("%d", &m);
  a=(int*) malloc(sizeof(int) * m);
  for (c = 0; c < m; c++)
    scanf("%d", &a[c]);
  scanf("%d", &n);
  b=(int*) malloc(sizeof(int) * n);
  for (c = 0; c < n; c++) 
    scanf("%d", &b[c]);
  sorted=(int*) malloc(sizeof(int) * (m+n));
  merge(a, m, b, n, sorted);
  if((m+n)%2==0)
  {
	  k=(m+n)/2;
	  r=(sorted[k]+sorted[k+1])/2;
	  printf("median = %f",r);
  }
  else
  {
	  k=(m+n)/2;
	  printf("median = %d",sorted[k]);
  }
  getch();
  return 0;
}
 
void merge(int a[], int m, int b[], int n, int sorted[]) {
  int i, j, k;
 
  j = k = 0;
 
  for (i = 0; i < m + n;) {
    if (j < m && k < n) {
      if (a[j] < b[k]) {
        sorted[i] = a[j];
        j++;
      }
      else {
        sorted[i] = b[k];
        k++;
      }
      i++;
    }
    else if (j == m) {
      for (; i < m + n;) {
        sorted[i] = b[k];
        k++;
        i++;
      }
    }
    else {
      for (; i < m + n;) {
        sorted[i] = a[j];
        j++;
        i++;
      }
    }
  }
}
