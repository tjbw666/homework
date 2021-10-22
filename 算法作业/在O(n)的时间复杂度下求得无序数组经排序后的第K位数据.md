### 1、在O(n)的时间复杂度下求得无序数组经排序后的第K位数据

``` c++
#include<iostream>
#include<algorithm>
using namespace std;

int kthSmallest(int arr[], int n, int k)
{
    // 排序
    sort(arr, arr + n);

    // 返回数组的第k位数据
    return arr[k - 1];
}

int main()
{
    int k;
    int arr[] = { 12, 3, 5, 7, 19 };
    int n = sizeof(arr) / sizeof(arr[0]);
    cout << "你要找第几位数据: " << endl;
    cin >> k;
    cout << "The element is " << kthSmallest(arr, n, k);
    return 0;
}
```



