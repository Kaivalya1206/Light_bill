# Light_bill
#include<iostream> using namespace std; class user
{
public:
string name; int mn;
void getdata(string pname)
{
name=pname;
}
void getdata(int pmn)
{
mn=pmn;
}
};
class electricity:public user
{
private:
int mn,pu,cu,n;
 
float bill; public:
electricity()
{
bill=0;
}
void getdataf(void); int process(void); void calculate(void); void display(void);
~electricity(){}
};
void electricity::getdataf(void)
{
cout<<"Enter user Name:"; string name; getline(cin,name); getdata(name); cout<<"Enter meter No."; cin>>mn;
getdata(mn);
cout<<"\n Enter the privious units:"; cin>>pu;
cout<<"\n Enter the current units:";
 
cin>>cu;
}
int electricity::process(void)
{
if(cu>pu)
{
n=cu-pu; return(1);
}
else return(0);
}
void electricity::calculate(void)
{
int dn; dn=n; if(dn<=50)
{
bill=bill+(dn*2);
}
else
{
bill=bill+(50*2); if(dn<=200)
 
{
dn=dn-50; bill=bill+(dn*3.5);
}
else
{
bill=bill+(150*3.5); if(dn<=500)
{
dn=dn-200; bill=bill+(dn*4.5);
}
else
{
bill=bill+(300*4.5); dn=dn-500; bill=bill+(dn*5);
}}}}
void electricity::display(void)
{
cout<<"\nName:"<<name; cout<<"\n Meter no."<<mn; cout<<"\n Privious unit"<<pu; cout<<"\n Current unit"<<cu;
cout<<"\n No. of units consumed :"<<n; cout<<"\n Bill :"<<bill;
}
int main()
{
electricity E; int a;
abc:system("cls"); E.getdataf(); a=E.process(); if(a==0)
{
cout<<"\n Wrong data Reenter it"; goto abc;
}
else
{
E.calculate(); E.display();
}}
