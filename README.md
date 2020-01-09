#include <iostream>

using namespace std;

int front=-1,rear=-1;

void insertion(int arr[],int n)
{
    if(rear>=n-1)
    {
        cout << "Queue Overflow!!!\n";
    }
    else if(rear==-1)
    {
        front=0;
        rear++;
        cout << "Enter Value to be Enqueued: ";
        cin >> arr[rear];
    }
    else
    {
        rear++;
        cout << "Enter Value to be Enqueued: ";
        cin >> arr[rear];
    }
}

void deletion(int arr[],int n)
{
    if(front==-1 || front>rear)
    {
        cout << "No Value Present to dequeue!!!\n";
    }
    else if(front<=rear)
    {
        cout << "Value Dequeued : " << arr[front] << endl;
        front++;
    }
}

void display(int arr[],int n)
{

    if(front==-1 ||  front>rear)
    {
        cout << "No Value Present in Queue!!!\n";
    }
    else
    {
        cout << "Values Of Queue: ";
        for(int i=front; i<=rear; i++)
        {
            cout << arr[i] << " ";
        }
        cout << endl;
    }
}

int main()
{
    int n,i;
    cout << "Enter size of Queue: ";
    cin >> n;
    int *arr=new int[n];
    cout << "For Insertion Enter 1" << endl;
    cout << "For Deletion Enter 2" << endl;
    cout << "For Display Enter 3" << endl;
    cout << "For Exit Enter 4" << endl;
    while(true)
    {
        cout << "Enter the choice: ";
        cin >> i;
        switch(i)
        {
        case 1:
            insertion(arr,n);
            break;
        case 2:
            deletion(arr,n);
            break;
        case 3:
            display(arr,n);
            break;
        case 4:
            break;
        }
        if(i==4)
        {
            break;
        }
    }
    return 0;
}
