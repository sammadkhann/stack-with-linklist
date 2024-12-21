# stack-with-linklist

stack.h

#include "Node.h"
class Stack
{
private:
	Node* top;
public:
	Stack();
	void push(int);
	void pop();
	bool isEmpty();
	//int getTop();
	void print();
};

Node.h
#include <iostream>
using namespace std;
class Node
{
private:
	int data;
	Node* next;

public:
	Node()
	{
		data = 0;
		next = NULL;
	}
	Node(int value)
	{
		data = value;
		next = NULL;

	}
	void setData(int value)
	{
		data = value;
	}
	void setNext(Node* link)
	{
		next = link;
	}
	int getData()
	{
		return data;
	}
	Node* getNext()
	{
		return next;
	}
};

imp.cpp

#include "Stack.h"
#include<iostream>
using namespace std;

Stack::Stack()
{
	//yeh top head kiy tharah work kare ga
	top = NULL;
}
bool Stack::isEmpty()
{
	if (top == NULL)
	{
		return true;
	}
	else
	{
		return false;
	}
}

	void Stack::push(int value)
	{
		if (isEmpty())
		{
			Node* temp = new Node(value);
			top = temp;
		}
		else
		{
			Node* temp = new Node(value);
			temp->setNext(top);
			top = temp;
		}

	}
	void Stack::pop()
	{
		Node* temp = top;
		top = top->getNext();
		delete temp;
	}


void Stack::print()
{
	Node* temp = top;
	while (temp != NULL)
	{
		cout << temp->getData() << endl;
		temp = temp->getNext();
	}
}


main.cpp

#include "Stack.h"
#include<iostream>
#include<conio.h>
using namespace std;
int main()

{
	Stack S;
	S.push(2);
	S.push(5);
	S.push(9);
	S.push(10);
	S.push(12);

	S.print();

	S.pop();
	S.pop();

	S.print();

	getch();
	return 0;
}
