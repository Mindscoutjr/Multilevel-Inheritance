#include <iostream>
using namespace std;
class employee
{
    protected:
        int AttendanceNumber;
    public:
        void get_number(void);
        void put_number(void);
};
void employee :: get_number(int a)
{
    AttendanceNumber = a;
}
void employee :: put_number()
{
    cout<<"Attendance Number\n"<<AttendanceNumber<<"\n";
}
class assignment : public employee                    //ist level inheritance
{
    protected:
        float asi1;
        float asi2;
    public:
        void get_score(float,float);
        void put_score(void);
};
void assignment :: get_score(float x,float y)
{
    asi1=x;
    asi2=y;
}
void assignment :: put_score()
{
    cout<<"marks on assignment 1\n"<<asi1<<"\n";
    cout<<"marks on assignment 2\n"<<asi2<<"\n";
}
class result : public assignment
{
    float total;
    public :
        void display(void);
};
void result :: display(void)
{
    total=asi1+asi2;
    put_number();
    put_score();
    cout<<"total="<<total<<"\n";
    
}
int main()
{
    result employee1;
    employee1.get_number(111);
    employee1.get_score(85.0,90.0);
    employee1.display();
    return 0;
}
