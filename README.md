///////////////  HEADER_1  //////////////////////
#pragma once
#include <iostream>
#include <vector>
#include <string>
using namespace std;

struct FIO {
	string Name;
	string Surname;
	vector <int> Grades;
};
void input();
void Addition();


///////////////////////////////////////////////////






/////////     MAIN_CPP     ////////////////////////
#include <iostream>
#include <iomanip>
#include <cmath>
#include <vector>
#include <string>
#include "Header.h";
using namespace std;

FIO* st;

void input() {
	cout << "Please, input yout data" << endl;
	FIO s;
	int a;
	int temp = 0, ave = 0;
	cout << "1. Name: ";
	cin >> s.Name;
	cout << "2. Surname: ";
	cin >> s.Surname;
	cout << "3. Grades` list: ";
	for (int i = 0; i <= 9; i++) {
		cin >> a;
		s.Grades.push_back(a);
		temp += s.Grades[i];
		ave = temp / 10;
	};
	cout << endl;
	cout << "-------------------------------------------------\n";
	cout << "4. Average: " << ave << endl;
	cout << "-------------------------------------------------\n";
	if (ave >= 4)
		cout << "5. Exam is accepted\n";
	else
		cout << "5. Exam is not accepted\n";

};


void Addition() {
	cout << "\n\n\tADDING A GRADE\n";
	cout << "Enter a grade to add\n";
	FIO s;
	cout << "New grades` list: ";
	int a;
		cin >> a;
		s.Grades.push_back(a);
	cout << endl;
}

void Grades() {

};

int main()
{
	FIO st;
	int choice;
	do {
		cout << "\tMENU\n";
		cout << "  1. Add student`s data ......  1\n";
		cout << "  2. Add a grade   ...........  2\n";
		cout << "  3. Output list  ............  3\n";
		cout << "  4. Student`s grades  .......  4\n";
		cout << "  5. Debtor students  ........  5\n";
		cout << "  6. EXIT ....................  6\n";
		cout << "-> ";
		cin >> choice;
		switch (choice) {
		case 1: (choice == 1); {
			cout << "\tINPUT\n";
			input();
			break;
		};
		case 2: (choice == 2); {
			void Addition();
			break;
		};
		case 3: (choice == 3); {

			break;
		};
		case 4: (choice == 4); {

			break;
		};
		default:
			cout << "Someting wrong. Try again.\n";
		}
	} while (choice != 6);
}




