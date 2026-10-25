#include <iostream>
using namespace std;

void libraryMenu(){
    cout<<"Library Menu:\n1. Check out a book.\n2. Return a book.\n3. View the number of books available.\n4. Close the menu.";
}

void BOOKS(){
    cout << "\n1. Maths\n2. Physics\n3. Chemistry\nEnter your choice: ";
}


int choosen(int& x, int& maths, int& physics, int& chemistry ){
    cout <<"\n";
    int bookChoice;
    switch (x){
        case 1:
            cout << "What book do you want to checkout?";
            BOOKS();
            cin >> bookChoice;
            if (bookChoice==1&&maths>0){
                maths--;
                cout<< "Maths checked out\n";
            } else if (bookChoice==3&&chemistry>0){
                chemistry--;
                cout<< "Chemistry checked out\n";
            } else if (bookChoice==2&&physics>0){
                physics--;
                cout<< "Physics checked out\n";
            }
            break;
        case 2:
            cout << "What book do you want to return?";
            BOOKS();
            cin >> bookChoice;
            if (bookChoice==1){
                maths++;
                cout<< "Maths returned\n";
            } else if (bookChoice==3){
                chemistry++;
                cout<< "Chemistry returned\n";
            } else if (bookChoice==2){
                physics++;
                cout<< "Physics returned\n";
            }
            break;
        case 3:
            cout <<"1. Maths = "<< maths <<"\n2. Physics = "<< physics <<"\n3. Chemistry = " << chemistry;
            cout << endl;
            break;
        case 4:
            cout <<"You exited the menu.";
            break;
        default:
            cout <<"Invalid choice.";
            x = 4;
    }
    return 0;
}
void bill(int x,int y,int z){
    if (x>3){
        cout << "\nMaths book returned:" << x-3;
    }else{
        cout << "\nMaths books checked out:" << 3-x;
    }
    if (y>5){
        cout << "\nPhysics book returned:" << y-5;
    }else{
        cout << "\nPhysics books checked out:" << 5-y;
    }
    if (z>6){

        cout << "\nChemistry book returned:" << z-6;
    }else{
        cout << "\nChemistry books checked out:" << 6-z;
    }
}
int main (){
    int maths=3,physics=5,chemistry=6;
    
    int x = 0;
    while(x!=4){
    libraryMenu();
    cout << "\nEnter your choice: ";
    cin >> x;
    choosen(x, maths, physics , chemistry);
    }
    bill(maths, physics, chemistry);
return 0;
}