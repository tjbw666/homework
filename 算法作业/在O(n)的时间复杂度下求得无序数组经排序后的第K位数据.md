1. ## 在O(n)的时间复杂度下求得无序数组经排序后的第K位数据

   ## QuickSort.h

   ``` c++
   #pragma once
   
   class  QuickSortInternalPractice
   {
   public:
       int  findKth(int a[15], int n, int K)
       {
           return findKth(a, 0, n - 1, K);
       }
   
       int  findKth(int a[15], int low, int high, int K)
       {
           int part = partition(a, low, high);
           if (part - low + 1 == K) {
               return a[part];
           }
           else if (part - low + 1 < K) {
               return findKth(a, part + 1, high, K - part + low - 1);
           }
           else {
               return findKth(a, low, part - 1, K);
           }
       }
   
       int partition(int a[15], int low, int high)
       {
           int key = a[low];
           while (low < high)
           {
               while (low < high && a[high] <= key)
               {
                   high--;
               }
               a[low] = a[high];
               while (low < high && a[low] >= key)
               {
                   low++;
               }
               a[high] = a[low];
           }
           a[low] = key;
           return low;
       }
   
   
   };
   ```

   

   ## main.cpp

   ``` c++
   #include<iostream>
   #include"QuickSort.h"
   using namespace std;
   
   int main()
   {
   	
   	int a[15] = { 1,1,4,32,12,3,4,1,23,141,3,213,1,4,6 };
   
   	
   	QuickSortInternalPractice q;
   	q.partition(a,0,14);
   	int b = q.findKth(a, 15, 4);
   	for (int i = 0; i < 15; i++)
   	{
   		cout << a[i] << " ";
   	}
   	cout << endl;
   	cout << "第四个数据是: " << endl;
   	cout << b << endl;
   }
   
   
   ```

   

   