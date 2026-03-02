#include <iostream>
#include <vector>
#include "Student.h" // Include the class we made above

void showMenu() {
    cout << "\n--- Digital Attendance System ---" << endl;
    cout << "1. Register Student" << endl;
    cout << "2. View All Students" << endl;
    cout << "3. Search Student by Index" << endl;
    cout << "0. Exit" << endl;
    cout << "Enter choice: ";
}

int main() {
    vector<Student> database; // Temporary storage in memory
    int choice;

    do {
        showMenu();
        cin >> choice;

        if (choice == 1) {
            string n, idx, p;
            cout << "Enter Name: "; cin.ignore(); getline(cin, n);
            cout << "Enter Index Number: "; cin >> idx;
            cout << "Enter Programme: "; cin.ignore(); getline(cin, p);
            
            database.push_back(Student(n, idx, p));
            cout << "Student Registered successfully! [cite: 38]" << endl;

        } else if (choice == 2) {
            cout << "\n--- Registered Students ---" << endl;
            for (auto &s : database) {
                s.displayStudent(); // [cite: 39]
            }
        }
        // Add Search logic here for choice 3 

    } while (choice != 0);

    return 0;
}
