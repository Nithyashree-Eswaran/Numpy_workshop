#include<iostream>
#include<string>
using namespace std;
//Aggregation is process of using data members of one class to another class//

class Address   //class hold address of person//
{
	public:
		string state,country;
		Address(string state,string country)
		{
			this->state=state;
			this->country=country;
		}
};
class Person              //class hold person name//
{
	private:
	    Address* add;          //reference to address class//
	public:
	    string name;
	    Person(string name,Address* add)
	    {
	    	this->name=name;
	    	this->add=add;
		}
		void disp()
		{
			
			cout<<"NAME......"<<"   "<<"ADDRESS......"<<endl<<endl;
			cout<<name<<"   "<<add->state<<"   "<<add->country<<endl<<endl
			;
		}
};
int main()
{
	Address a1("Seoul","South Korea");
    Address a2("Busan","South Korea");
	Person p1("RM",&a1);;
	p1.disp();
	Person p2("JIMIN",&a2);
	p2.disp();
	return 0;
}
