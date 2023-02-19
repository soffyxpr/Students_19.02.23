///////////////  HEADER_1  //////////////////////
#pragma once
#include <iostream>
#include <string>
#include <vector>
using namespace std;

struct FIO {
	string id = "123456";
	string name = "Abc";
	string surname = "Defgh";
	vector<int> vec{ 1,2,3,4,5,6,7,8,9,10 };

};

FIO input();
///////////////////////////////////////////////////






/////////     MAIN_CPP     ////////////////////////
#include <iostream>
#include <iomanip>
#include <cmath>
#include "header_1.h"
using namespace std;

int main()
{
	int choice;
	cout << "\t   MENU\n";
	cout << "  1. Add student`s data ......  1\n";
	cout << "  2. Add a grade   ...........  2\n";
	cout << "  3. Output list  ............  3\n";
	cout << "  4. Student`s grades  .......  4\n";
	cout << "  5. Debtor students  ........  5\n";
	cout << "  6. EXIT ....................  6\n";
	cout << "-> ";
	cin >> choice;
	cout << endl << endl;
	switch (choice) {
	case 1: (choice == 1); {
		FIO student = input();
		break;
	};
	case 2: (choice == 2); {

		break;
	};
	case 3: (choice == 3); {

		break;
	};
	case 4: (choice == 4); {

		break;
	};
	case 5: (choice == 5); {

		break;
	};
	case 6: (choice == 6); {
		
		break;
	};
	}


}

FIO input() {
	printf("\x1B[36;2m\tStudent`s form\n \033[0m");
	cout << "-------------------------\n";
	FIO s;
	int temp = 0, ave = 0;
	printf("\x1B[36;1m1. ID: \033[0m");
	cin >> s.id;
	printf("\x1B[36;1m2. Name: \033[0m");
	cin >> s.name;
	printf("\x1B[36;1m3. Surname: \033[0m");
	cin >> s.surname;
	cout << "-------------------------\n";
	printf("\x1B[36;1m4. Grades list: \033[0m");
	for (int i = 0; i < s.vec.size(); i++)
	{
		cin >> s.vec[i];
		temp += s.vec[i];
		ave = temp / 10;
	}
	cout << endl;
	/*for (int i = 0; i < s.vec.size(); i++)
	{
		cout << s.vec[i] << '|';
	} */
	printf("\x1B[36;1m5. Average: \033[0m");
	cout << ave << endl;
	cout << "-------------------------\n";
	if (ave >= 4)
		printf("\x1B[32;1mExam is accepted\n\033[0m");
	else
		printf("\x1B[31;1mExam is not accepted\n\033[0m");
	return s;
}
