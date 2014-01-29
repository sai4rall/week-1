/* To store the digits of a number in a linked list */
#include<stdio.h>
#include<conio.h>
#include<stdlib.h>
struct node
{
	int val;
	node *link;
}*p;
void insert(int n);
void display();
int main()
{
	p=NULL;
	int n,r;
	scanf("%d",&n);
	while(n!=0)
	{
		r=n%10;
		insert(r);
		n=n/10;
	}
	display();
	getch();
	return 0;
}
void insert(int r)
{
	struct node *temp;
	temp= (struct node *)malloc(sizeof(struct node));
	temp->val=r;
    temp->link=p;
	p=temp;
}
void display()
{
	struct node *temp;
	temp=p;
	while(temp!=NULL)
	{
		printf("%d",temp->val);
		temp=temp->link;
	}
}

