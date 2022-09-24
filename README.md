# Assignment-1
# This is the Header file "integer.h"
#ifndef INTEGER_H_
#define INTEGER_H_

class Integer
{
public:

	void display(int* Integer, int i);
	int Index(int* integer, int i, int x);
	int modify(int* Integer, int y, int z, int number);
	
};
#endif



# This is integer.cpp file.


#include <iostream>
#include <fstream>
#include <string>

#include "integer.h"


using namespace std;

void Integer::display(int* Integer, int number )
{
	cout << endl;
	cout << " Display : " << endl;
	cout << endl;
	for (int i = 0; i < number; i++)
	{

		cout << " " << Integer[i];
			
	}
	
	   cout << endl;
	   
};

int Integer::Index(int* integer, int number, int x)
{
	int searchindex;
	bool Integerfound;
	int i;

	Integerfound = false;

	for (i = 0; i < 100; i++)
	{
		if (x == integer[i] && !Integerfound)
		{

			searchindex = i;
			Integerfound = true;
		}
	}
	if (Integerfound)
	{
		cout << " Integer is present " << endl;
		cout << endl;
		cout << " Integer found at index : " << searchindex << endl;
	}
	else
	{
		cout << " Integer is not present ";
	}
	return 0;
}
int Integer::modify(int* Integer, int y, int z, int number)
{
	if (y > number) 
	{
		cout << "that index is not found.";
		system("pause");
		return 0;
		cout << endl;
	}
	if (y < 0)
	{
		cout << "that index is not is not found.";
		system("pause");
		return 0;
		cout << endl;
	}

	int beforeValue = Integer[y];
	Integer[y] = z;
	return beforeValue;

}

	
int main()
{
	Integer I; // Class

	
	//Declare

	int* Integer = new int[100];
	int i = 0;

	// Open file
	ifstream myFile;
	myFile.open("integers.txt.txt");


	for ( i = 0; i < 100; i++)
	{
			 myFile >> Integer[i];

	}

	int number = i;
	
	cout << " Total Number of integers are : " << number;
	cout << endl;

	I.display(Integer, number);
	cout << endl;
	
	//finding the location of the integer in the array

	//declaring the input value
	int x;

	cout << " Enter the Integer : ";
	cin >> x;
	cout << endl;

	I.Index(Integer, number, x);
	cout << endl << endl;


	int y;
	cout << " Enter the index to modify : ";
	cin >> y;
	cout << endl;

	int z;
	cout << " Enter the New Value for the index : ";
	cin >> z;

	int beforeValue = I.modify(Integer, y, z , number);

	I.display(Integer, number);

	cout << endl;



	system("pause");
	return 0;
}
  
  
  
#File used  "integer.txt" 
  
23 44 55 60 71 82  5 12 90 68
 2 10 70 54 22 53 87 81 20 41
16  0 52 64 47 26 38 66 85 73
51 72 61 24 46 35 56 65 74 83
92 63 32  8 17 97 78 57 21  9
42 11  1 31 91 62  3 13 33 43
93  4 14 34 84 94  6 15 37 25
95 76 80 19 30 99 40 50 96 98
75 45 86 77 67 36 27 18 88 59
79 58 29 28 49 48 39 89 69  7
  
 # when you run the code this is what you see.
 ![my code](https://user-images.githubusercontent.com/113943791/192078830-ed8dd1c9-b737-4dae-9d88-467b2a6508ee.png)

