//Project: Chall08
// Program that tells the denomination and number of notes required to 
// tender a particular amount

#include <iostream>
#include <iomanip>
using namespace std;

void numtender(int);
int main()
{
    int amount;

    cout << "Enter the amount to be tendered:  " <<endl;
    cin >> amount;
    numtender(amount);

    return 0;
}

void numtender(int amount)
{
    int den[] = { 1, 2, 5, 10, 20, 50, 100, 200, 500, 2000 };
    int numofnotes;

    if(amount <=0 )
    return;

    cout<<"Denomination detail:  "<<endl;
    for (int i = 8; i >= 0; --i)
    {
        if (amount>=den[i])
        {
            numofnotes = amount/den[i];
            cout<<setw(4)<<den[i]<<"x"
                <<setw(3)<<numofnotes <<"="
                <<setw(8)<<den[i]*numofnotes<<endl;

                amount = amount % den[i];
                if(amount == 0)
                break;
        }
    }
}


