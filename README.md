#include<iostream>
using namespace std;
#include<bits/stdc++.h>

int sort1(int* arr, int n) {
    int m = 0;
    for (int i = 0; i < n; i++) {
        bool isswap = false;
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
                m++;
                isswap = true;
            }
        }
        if (!isswap) {
            break;
        }
    }
    return m;
}
int sort2(int* arr, int n) {
    int m1 = 0;
    for (int i = 0; i < n; i++) {
        bool isswap = false;
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] < arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
                m1++;
                isswap = true;
            }
        }
        if (!isswap) {
            break;
        }
    }
    return m1;
}

int main(){
     int n;
     cin>>n;
     int arr[n];
     for(int i=0;i<n;i++){
            cin>>arr[i];
     }
      int swaps1 = sort1(arr, n);
       int swaps2 = sort2(arr, n);
       int k=abs(swaps2-swaps1);
       cout<<min(swaps1,k);
     
}
