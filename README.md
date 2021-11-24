#include<bits/stdc++.h>
using namespace std;

int power(int x, unsigned int y)
{
	if( y == 0)
	{
		return 1;
	}
	if (y%2 == 0)
	{
		return power(x, y/2)*power(x, y/2);
	}
	return x*power(x, y/2)*power(x, y/2);
}


int order(int x)
{
	int n = 0;
	while (x)
	{
		n++;
		x = x/10;
	}
	return n;
}
int isArmstrong(int x)
{

	int n = order(x);
	int temp = x, sum = 0;
	int ans1,ans2;
	ans1=0;
	ans2=0;
	while (temp)
	{
		int r = temp%10;
		if(r%2==0)
		{
		    ans1+=r;
		}
		else
		{
		    ans2+=r;
		}
		sum += power(r, n);
		temp = temp/10;
	}


	return (sum == x)?ans1:ans2;
}

int main()
{
	int x = 407;
	cout << isArmstrong(x) << endl;
	x = 1541;
	cout << isArmstrong(x) << endl;
	return 0;
}


__For last 3 line __
Int x;
Cin>>x;
