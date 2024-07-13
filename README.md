# LINKED-QUEUE
#include <iostream>
using namespace std;


struct node
{
    int data;
    node* link;
};

node* front;
node* rear;
node* Q;
node* ptr;

void enqueue()
{
    Q = new node;
    int data;
    cout<<"Enter the data for next node =\n";
    cin>>Q->data;
    Q->link = NULL;
    rear->link = Q; // WE are attaching new node to previous node
    rear = Q;// now rear is pointing to the last node(new)
}

void dequeue()
{
    if(front == NULL)
    {
        cout<<"QUEUE UNDERFLOW!!";
        
    }
    else
    {
        ptr = front;
        front = front->link;
        ptr->link = NULL;
        delete ptr;
    }
}

void display()
{
    ptr = front;
    while(ptr!= NULL)
    {
        cout<<ptr->data<<endl;
        ptr = ptr->link;
    }
}


int main()
{
    Q = new node;
    int data;
    cout<<"Enter the data for the first node =\n";
    cin>>Q->data;
    Q->link = NULL;
    front = Q;
    rear = Q;
    // Make it menu driven
    enqueue();
    enqueue();
    enqueue();
    display();
    dequeue();
    display();
    

    return 0;
Linked queue
