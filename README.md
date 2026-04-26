#include<iostream>
#include<fstream>
using namespace std;

int arr[10];

void inputArray()
{
    for(int i = 0; i < 10; i++)
    {
        cin >> arr[i];
    }
}

void displayArray()
{
    for(int i = 0; i < 10; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;
}

int calculateSum()
{
    int sum = 0;
    for(int i = 0; i < 10; i++)
    {
        sum = sum + arr[i];
    }
    return sum;
}

void writeToFile()
{
    ofstream myfile;
    myfile.open("data.txt");
    for(int i = 0; i < 10; i++)
    {
        myfile << arr[i] << endl;
    }
    myfile.close();
}

void readFromFile()
{
    int temp[10];
    ifstream myfile;
    myfile.open("data.txt");
    for(int i = 0; i < 10; i++)
    {
        myfile >> temp[i];
        cout << temp[i] << " ";
    }
    cout << endl;
    myfile.close();
}

int main()
{
    inputArray();
    displayArray();

    int s = calculateSum();
    cout << s << endl;

    writeToFile();
    readFromFile();

    return 0;
}
