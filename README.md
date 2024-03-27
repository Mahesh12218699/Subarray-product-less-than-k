# Subarray-product-less-than-k
C++-Code to find the number of Contiguous subarrays whose product is less than k
// Online C++ compiler to run C++ program online
#include <iostream>
#include<vector>
using namespace std;
int numberofsubarrays(vector<int> a,int k){
    int count=0;
    int mul;
    for(int i=0;i<a.size();i++){
        if(a[i]<k){
            count++;
        }
    mul=a[i];
    for(int j=i+1;j<a.size();j++){
        mul=mul*a[j];
    if(mul<k){
        count++;
    }
    else{
        break;
    }
    }
}
return count;
}
int main() {
    // Write C++ code here
    vector<int> a;
    cout<<"Enter the size of the array: ";
    int n;
    cin>>n;
    cout<<"Enter the elements of the array: ";
    for(int i=0;i<n;i++){
        int k;
        cin>>k;
        a.push_back(k);
    }
    int j;
    cout<<"Enter the highest number: ";
    cin>>j;
    cout<<numberofsubarrays(a,j);

    return 0;
}
