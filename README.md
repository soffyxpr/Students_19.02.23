///////////////  HEADER_1  //////////////////////
#pragma once
#include <iostream>
#include <iomanip>
#include <cmath>
#include <string>
#include <vector>
using namespace std;

struct Student
{
    string Name;
    string Surname;
    string Patronymic;
    int Grades[10];
    string color;
};
Student* arr;

void input_arr();
void prosmotr_record(int i);
int search();

///////////////////////////////////////////////////






/////////     MAIN_CPP     ////////////////////////
#include <iostream>
#include <iomanip>
#include <cmath>
#include <string>
#include <vector>
#include "Header.h"
using namespace std;

Student* arr;
int size = -1;


void input_arr()
{
    int size = -1;
    cout << "Enter the size...";
    cin >> size;
    if (size < 1) size = 1;
    arr = new Student[size];
    for (int i = 0; i < size; i++)
    {
        cout << "Number -> " << i + 1 << ": " << endl;
        cout << "Name ..." << endl;
        cin >> arr[i].Name;
        cout << "Surname ..." << endl;
        cin >> arr[i].Surname;
        cout << "Patronymic ..." << endl;
        cin >> arr[i].Patronymic;
        cout << "Grade list ..." << endl;
        for (int i = 0; i < 10; i++) {
            cin >> arr[i].Grades;
        }
        cin >> arr[i].color;
    }
}
void prosmotr_record(int i)
{
    cout << "Number -> " << i + 1 << ": " << endl;
    cout << "Name..." << arr[i].Name << endl;
    cout << "Surname..." << arr[i].Surname << endl;
    cout << "Patronymic ..." << arr[i].Patronymic << endl;
    cout << "Grades list..." << arr[i].Grades << endl;
    cout << endl << endl;
}
void prosmotr_record(int i)
{
    int size = -1;
    if (size < 0) cout << "Array is not input!" << endl; else
        for (int i = 0; i < size; i++) prosmotr_record(i);
}
int search()
{
    int size = -1;
    if (size <= 0) cout << "Array is not input!" << endl; else
    {
        int menu_s;
        cout << "Input parameter to search..." << endl;
        cout << "1 - Name..." << endl;
        cout << "2 - Surname..." << endl;
        cout << "3 - Patronymic..." << endl;
        cout << "4 - Grades" << endl;
        cin >> menu_s;
        if (menu_s != 6)
            cout << "Input example to find..." << endl; else
            cout << "<= 0 - automatic, >=1 - manual ..." << endl;
        float obr;
        string obr_color;
        if (menu_s <= 6)  cin >> obr;
        else      cin >> obr_color;
        int count_s = 0;
        for (int i = 0; i < size; i++)
        {
            int temp[10];
            int temp1;
            string temp_color;
            switch (menu_s)
            {
            case 1: {
                temp_color = arr[i].Name;
                break; }
            case 2: {
                temp_color = arr[i].Surname;
                break; }
            case 3: {
                temp_color = arr[i].Patronymic;
                break; }
            case 4: {
                for (int i = 0; i < 10; i++)
                {
                    temp[i] = arr[i].Grades;
                }
                break; }
            case 5: {
                temp_color = arr[i].color;
                break; }
            }
            if (menu_s <= 6)
            {
                if (temp1 == obr) {
                    prosmotr_record(i);
                    count_s++;
                }
            }
            else {
                if (temp_color == obr_color)
                {
                    prosmotr_record(i);
                    count_s++;
                }
            }
        }
        return count_s;
    }
    return 0;
}

int main()
{
    int size = -1;
    bool ok = true;
    short menu = -1;
    do
    {
        cout << "MENU" << endl;
        cout << "1 - add student;" << endl;
        cout << "2 - output student`s form;" << endl;
        cout << "3 - search parameter;" << endl;
        cout << "any key - exit." << endl;
        cout << "Press menu key...";
        cin >> menu;
        switch (menu)
        {
        case 1:
            input_arr();
            break;
        case 2:
            output_arr();
            break;
        case 3:
        {
            int count = search();
            (count == -1) ? cout << "record is not search!" << endl :
                (size < 0) ? cout << "Error search!" << endl : cout << "record search count: " << count << endl;
            break;
        }
        default:
            ok = false;
            break;
        }
        if (menu <= 3 && menu >= 1) {
            string ext;
            cout << "OK! Press any key!\n\n";
            cin >> ext;
        }
    } while (ok);
    cout << "DONE!";
    return 0;
}
}
