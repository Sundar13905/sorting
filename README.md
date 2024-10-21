# Experiment 20  
### To study and implement Sorting Algorithm 
### i) Selection Sort  ii) Insertion Sort   iii) Bubble Sort

## Aim :-
To execute and run different sorting algorithms 

## Theory 

Sorting in C++ is the process of arranging data (such as integers, strings, or objects) in a particular order, typically ascending or descending.
C++ provides a variety of algorithms and tools to perform sorting, with different properties, advantages, and disadvantages depending on the algorithm used.

## Bubble Sort
Bubble Sort is a simple comparison-based algorithm where adjacent elements are repeatedly swapped if they are in the wrong order.

### Properties:
Time Complexity:
Best case: O(n) (if the data is already sorted)

Average and Worst case: O(n²)
Space Complexity: O(1) (in-place)

### Advantages:
1. Simple to implement.
2. Efficient for small data sets or nearly sorted data.
   
### Disadvantages:

1. Highly inefficient for large data sets due to O(n²) complexity.
2. Rarely used in practical scenarios except for educational purposes.
## Insertion Sort
Insertion Sort works by repeatedly taking the next element from the unsorted part and inserting it into its correct position in the sorted part.

### Properties:
Time Complexity:
Best case: O(n) (if data is already sorted)
Worst and Average case: O(n²)
Space Complexity: O(1)

### Advantages:
1. Simple to implement and efficient for small or nearly sorted arrays.
2. Online sorting: Can sort data as it arrives.
   
### Disadvantages:
1. Poor performance on large, unsorted data sets due to O(n²) time complexity.

## Selection Sort
Selection Sort works by repeatedly selecting the minimum (or maximum) element from the unsorted portion and placing it at the end of the sorted portion.

### Properties:
Time Complexity: O(n²)
Space Complexity: O(1) (in-place)

### Advantages:
1. Simple to implement.
2. In-place sorting, requiring no extra memory.
 
### Disadvantages:
1. Inefficient for large datasets, as it always performs O(n²) comparisons.
2 .Not stable, and rarely used in real-world applications.

## Code: -
## Selection Sort
~~~
// C++ program to implement Selection Sort
#include <iostream>
#include<vector>
using namespace std;

void selectionSort(vector<int> &arr) {
    int n = arr.size();

    for (int i = 0; i < n - 1; ++i) {
        int min_idx = i;
        for (int j = i + 1; j < n; ++j) {
            if (arr[j] < arr[min_idx]) {
                min_idx = j; 
            }
        }

        swap(arr[i], arr[min_idx]);
    }
}

void printArray(vector<int> &arr) {
    for (int &val : arr) {
        cout << val << " ";
    }
    cout << endl;
}

int main() {
    vector<int> arr = {64, 25, 12, 22, 11};

    cout << "Original array: ";
    printArray(arr); 

    selectionSort(arr);

    cout << "Sorted array: ";
    printArray(arr);

    return 0;
}

~~~

### Insertion Sort

~~~
#include <iostream>
using namespace std;

void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;

        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}

int main() {
    int arr[] = {64, 25, 12, 22, 11};
    int n = sizeof(arr) / sizeof(arr[0]);

    cout << "Original array: ";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    insertionSort(arr, n);

    cout << "\nSorted array: ";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}

~~~

## Bubble sort
~~~
#include<iostream>
using namespace std;

void swap(int* a,int* b){
    int temp;
    temp=*a;
    *a=*b;
    *b=temp;
}
int main(){
    int elements;
    cout<<"How many elements in the array? :";
    cin>>elements;
    int array[elements];
    cout<<"Enter elements:";
    for(int i=0;i<elements;i++){
        cin>>array[i];
    }
    for(int i=0;i<elements;i++){
        cout<<array[i]<<" ";
    }
    int n=0;
    while(n!=elements){
        for(int i=0;i<elements-n;i++){
            if(array[i]>array[i+1]){
                swap(&array[i],&array[i+1]);
            }
        }
        n++;
    }
    cout<<"\nSorted array is:"<<endl;
    for(int i=0;i<elements;i++){
        cout<<array[i]<<" ";
    }
    return 0;
}

~~~

## Code Output






##  Conclusion
We learnt about different sorting algorithms and how to implement them in C++
