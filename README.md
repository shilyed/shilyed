

#include<iostream>
using namespace std;

typedef struct node
{
	char diqu[100];
	int fengxian;
	struct node *next;

	
fxdq * createList(int n) 
{
	fxdq * head = new fxdq;
	fxdq * pre = head;
	// fxdq head;
	 
	for (int i = 0 ; i < n ; i++)
	{
		fxdq *p = new fxdq;
		cout  <<  "请输入第" << i+1 <<  "个地区的数据的数据（先输入地区名，后输入风险等级）" << endl ;
		cin >> p->diqu;
		cin >> p->fengxian;
		
		pre->next = p;
		pre = p;
		p -> next = NULL;
	}
	 return head;
}

void display(fxdq *head)
{
	fxdq*p = head -> next;
	while(p != NULL)
	{
		cout << p-> diqu << "," << p -> fengxian;
		p = p -> next ;
	}
}

int main()
{
	cout << "全国风险地区查询" << endl; 
	int n = 5;
	fxdq *head = createList (5);
	
	int a ;
	cout << "请问需要查询什么" << "1. 风险地区汇总,2. 某地风险情况" ;
	cin >> a ;
	if (a == 1)
	 display (head);

	return 0;
}
