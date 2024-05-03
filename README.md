#include<stdio.h>
#include<stdlib.h>

void create(int);
void display();

struct node
{
   int data;
   struct node *next;
}*head;

int main()
{
    int n=4;
    create(n);
    display();
}

void create(int n){
    int data;
    struct node *temp,*newnode;
    head=(struct node*)malloc(sizeof(struct node));
    scanf("%d",&data);
    head->data=data;
    head->next=NULL;
    temp=head;
    for(int i=2;i<=n;i++)
    {
        newnode=(struct node*)malloc(sizeof(struct node));
        scanf("%d",&data);
        newnode->data=data;
        newnode->next=NULL;
        temp->next=newnode;
        temp=temp->next;
    }
}

void display()
{
    struct node *temp;
    temp=head;
    while(temp!=NULL)
    {
        printf("%d ",temp->data);
        temp=temp->next;
    }
}
