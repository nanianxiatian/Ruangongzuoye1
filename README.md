# Ruangongzuoye1
打印出简单的四则运算
//简单的四则运算，用随机数实现
//2016 3 7 Sunzhe
#include<iostream>
using namespace std;

void main()
{
	int x;//进行选择的数
	q:cout<<"请选择要进行的运算：1.整数运算 2.真分数运算 3.退出程序"<<endl;
	cin>>x;
	switch(x)//进行整数的运算
	{
	case 1:
		{
			for(int i=0;i<30;i++)
			{
				int n=rand() %4;//产生随机数,运算符的

				int a=rand()%100;//产生1~100随机数
				int b=rand()%100;//产生1~100随机数
				
				if(n==0){
					cout<<a<<"+"<<b<<"="<<endl;
				}
				else if(n==1){
					cout<<a<<"-"<<b<<"="<<endl;
				}
				else if(n==2){
					cout<<a<<"*"<<b<<"="<<endl;
				}
				else{
					if(b==0){
						b++;
					}
					cout<<a<<"/"<<b<<"="<<endl;
				}
			}
			goto q;
		}
	case 2:
		{
			for(int i=0;i<30;i++)
			{
				int c=rand()%100;//产生1~100随机数
				int d=rand()%100;//产生1~100随机数
				int e=rand()%100;//产生1~100随机数
				int f=rand()%100;//产生1~100随机数

				
				//保证为真分数
				if(c>d)
				{
					int t;
					t=d;
					d=c;
					c=t;
				}
				if(e>f)
				{
					int s;
					s=f;
					f=e;
					e=s;
				}
				if(d==0){d++;}  //分母不为零
				if(f==0){f++;}  //分母不为零
				//约分化为最简
				for(int a=c;a>0;a-- )
				{
					if(c%a==0&&d%a==0)
					{
						c=c/a;
						d=d/a;
						break;
				    }
				}
				for(int b=e;b>0;b-- )
				{
					if(e%b==0&&f%b==0)
					{
						e=e/b;
						f=f/b;
						break;
				    }
				}

				int n=rand() %4;   //产生运算符的随机数
				
				if(n==0){
					cout<<c<<"/"<<d<<"+"<<e<<"/"<<f<<"="<<endl;
				}
				else if(n==1){
					cout<<c<<"/"<<d<<"-"<<e<<"/"<<f<<"="<<endl;
				}
				else if(n==2){
					cout<<c<<"/"<<d<<"*("<<e<<"/"<<f<<")="<<endl;
				}
				else
				{
					cout<<c<<"/"<<d<<"/("<<e<<"/"<<f<<")="<<endl;
				}
			}
			goto q;
		}
	case 3:
		{
			exit(0);
		}

	}
}
