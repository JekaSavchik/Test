# Test
Test LIGHT ACADEMY
#include <iostream>
#include <vector>
#include <math.h>
#include <conio.h>
using namespace std;

int input();
double mean_square(vector<int> _A);

void main()
{
	int tmp = 0;
	vector<int> A;
	do
	{
		system("CLS");
		cout << "\n\tEnter the number of values to calculate the mean square" << endl;
		tmp = input();
		system("CLS");
		printf("Enter %d values\n", tmp);
		for (int i(0); i < tmp; i++)
			A.push_back(input());
		system("CLS");
		cout << "mean square - " << mean_square(A) << endl;
		A.clear();
		cout << "\n\n\n\tEsc - Exit            any key - a new calculation";
		tmp = getch();
	} while (tmp != 27);
}

/////////////////////////
int input()
{
	int temporary;
	while (!(cin >> temporary) || cin.get() != '\n')
	{
		cin.clear();
		while (cin.get() != '\n')
			continue;
		cout << "\aInvalid input. Try again.";
	}
	return temporary;
}

double mean_square(vector<int> _A)
{
	vector<int>::iterator t; int B = 0;
	cout << "values for calculation\n\t->";
	for (t = _A.begin(); t != _A.end(); t++)
		cout << " " << *t;
	cout << endl << endl;
	for (t = _A.begin(); t != _A.end(); t++)
		B += pow(*t, 2);
	return sqrt(B / _A.size());
}
