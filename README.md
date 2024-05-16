"# stack" 

#include <iostream>
using namespace std;

#define max 10
int n;
int choice;

class plate {
public:
    int stack[max];
    int top = -1;
    int i;

    void push();
    void pop();
    void read();
};

void plate::push() {
    int val;
    if ((top+1) == n) {
        cout << "overflow!" << endl;
    }
    else {
        cout << "enter the value: ";
        cin >> val;
        top++;
        stack[top] = val;
    }
    /*while (i >= 0) {
        cout << "insert a number(capacity reach 5): ";
        cin >> n;
        number[i] = n;
        i++;
        top++;
        if (i == sizeof(number) / sizeof(int))
            break;
    }*/
}

void plate::pop() {
    if (top == -1) {
        cout << "underflow!" << endl << endl;
    }
    else {
        top--;
    }
}

void plate::read() {
    if (top == -1) {
        cout << "plate container is empty!" << endl << endl;
    }else{
        for (i = top; i >= 0; i--) {
            cout << stack[i] << endl;
        }
    }
}

int main() {
    plate kiew;

    cout << "enter the number of elements in the stack (max=10): ";
    cin >> n;

    while (choice != 4) {
        cout << "1. Push\n" << "2. Pop\n" << "3. Read\n" << "4. Exit the program.\n";
        cout << "enter ur choice: ";
        cin >> choice;

        switch (choice) {
        case 1: {
            kiew.push();
            break;
        }
        case 2: {
            kiew.pop();
            break;
        }
        case 3: {
            kiew.read();
            break;
        }
        case 4: {
            cout << "exit the program." << endl;
            break;
        }
        default:
            cout << "please enter a valid value." << endl;
        }
    }


    return 0;
}
