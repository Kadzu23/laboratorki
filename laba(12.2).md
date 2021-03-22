# #include <iostream>
#include <ctime>

using namespace std;

void randArr(int arr[] , int size)
{
	for (int i = 0; i <size; i++)
	{
		arr[i] = rand() % 10 + 1;
		cout << arr[i] << " ";
	}
}

int sum(int arr[] , int size)
{
	int min=0 , max=0 , sum=0;
	for (int i = 0; i < size; i++)
	{
		if (arr[max] < arr[i]) max = i;
		if (arr[min] > arr[i]) min = i;
	}
	cout << "max = " << arr[max] << " min = " << arr[min] << endl;
	if (min > max)
	{
		min += max;
		max = min - max;
		min -= max;
	}
	
	for (int i = min+1; i < max; i++)
	{
		sum +=arr[i];
	}
	return sum;
}

int main()
{
	const int size = 10;
	int array[size];
	srand(time(0));
	setlocale(LC_ALL, "ru");
	randArr(array , size);
	cout << "сумма между максимальным и минимальным элементами равно " << sum(array , size) << endl;
	system("pause");
	return 0;
}
