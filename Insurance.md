#include <iostream>
using namespace std;

class Insurance {
private:
    string name;
    int age;
    float policyAmount;
    string type;
    float premium;

public:
    void getData() {
        cout << "Enter Name: ";
        cin >> name;

        cout << "Enter Age: ";
        cin >> age;

        cout << "Enter Policy Amount: ";
        cin >> policyAmount;

        cout << "Enter Insurance Type (Life/Health): ";
        cin >> type;
    }

    void calculatePremium() {
        if (type == "Life" || type == "life") {
            if (age <= 25)
                premium = policyAmount * 0.05;
            else if (age <= 50)
                premium = policyAmount * 0.07;
            else
                premium = policyAmount * 0.10;
        }
        else if (type == "Health" || type == "health") {
            if (age <= 25)
                premium = policyAmount * 0.04;
            else if (age <= 50)
                premium = policyAmount * 0.06;
            else
                premium = policyAmount * 0.09;
        }
        else {
            cout << "Invalid Insurance Type!" << endl;
            premium = 0;
        }
    }

    void display() {
        cout << "\n--- Insurance Details ---" << endl;
        cout << "Name: " << name << endl;
        cout << "Age: " << age << endl;
        cout << "Policy Amount: " << policyAmount << endl;
        cout << "Insurance Type: " << type << endl;
        cout << "Premium: " << premium << endl;
    }
};

int main() {
    Insurance obj;

    obj.getData();
    obj.calculatePremium();
    obj.display();

    return 0;
}
