#include<iostream>
#define MaxSize 100
using namespace std;
int queue[MaxSize];
int front = -1;
int rear = -1;
void Enqueue(int value)
{
	if (rear != MaxSize - 1)
	{
		if (front == -1 && rear == -1)
		{
			front++;
			rear++;
			queue[rear] = value;
		}
		else
		{
			rear++;
			queue[rear] = value;
		}
		cout << value << " Is Added in Queue\n";
	}
	else
		cout << "Queue is Full Can't Add in it..\n";
}
void Dequeue()
{
	if (front != -1 && rear != -1 && front <= rear)
	{
		int value = queue[front];
		front++;
		cout << value << " Is Deleted From Queue\n";
	}
	else
		cout << "Queue is Empty Can't Delete From it..\n";
}
void Print_Queue()
{
	cout << "Your Queue is\n";
	for (int i = front; i <= rear; i++)
		cout << queue[i] << " ";
	cout << endl;
}
int main()
{
	int choise, value;
	cout << "\tWElcome To My Program\n";
	cout << "      -------------------------\n";
	cout << "1) Add Element in Queue\n" << "2) Delete Element From Queue\n" << "3) Display Queue\n" << "4) EXit\n";
	cout << "=========================\n";
	do
	{
		cout << "=========================\n";
		cout << "Enter Your Choise\n";
		cin >> choise;
		cout << "=========================\n";
		switch (choise)
		{
		case 1:
			cout << "Enter Element To Add in Queue\n";
			cin >> value;
			Enqueue(value);
			cout << "=========================\n";
			break;
		case 2:
			Dequeue();
			cout << "=========================\n";
			break;
		case 3:
			Print_Queue();
			cout << "=========================\n";
			break;
		case 4:
			cout << "EXiting...\n";
			break;
		default:
			cout << "Invalid Choise..!! Please Try again\n";
			cout << "=========================\n";
			break;
		}
	} while (choise != 4);
	return 0;
}
