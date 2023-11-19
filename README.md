# stack-using-single-linked-list
#include<stdio.h>
#include<stdlib.h>
struct node{
    int data;
    struct node*link;
};
struct node* root=NULL;
void push(){
    int d;
    printf("enter the data");
    struct node *temp;
    temp=(struct node*)malloc(sizeof(struct node));
    scanf("%d",&temp->data);
    if(root==NULL){
    root=temp;
    }
    else{
        temp->link=root;
        root=temp;
    }
}
void pop(){
    if(root==NULL)
    printf("stack under flow");
    else
        root=root->link;
}
void display(){
    struct node *temp;
    temp=root;
    while(temp!=NULL)
    {
        printf("%d\n",temp->data);
        temp=temp->link;
    }
}
void main()
{int n;
    while(1)
    {
       printf("give the value of n");
       scanf("%d",&n);
       switch(n)
       {
            case 1:
                push();
                break;
            case 2:
                pop();
                break;
            case 3:
                display();
                break;
            default:printf("hi");
       }
    }
}
