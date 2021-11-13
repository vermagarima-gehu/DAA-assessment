# DAA-assessment
WEEK 1
1-LINEAR SEACHING
 
#include<bits/stdc++.h>
using namespace std;
int main()
{
    int t;
    cin>>t;
    while(t--)
    {
        int n;
        cin>>n;
        vector<int> arr(n);
        for(int &i:arr)
            cin>>i;
        int key,i;
        cin>>key;
        for(i=0;i<n;i++)
        {
            if(arr[i]==key)
                break;
        }
        if(i==n)
            cout<<"Not Present "<<n<<endl;
        else
            cout<<"Present "<<i+1<<endl;
    }
    return 0;
}
                                        
                                       
2-//*BINARY SEARCHING
                                        
                                        
#include<bits/stdc++.h>
using namespace std;
void binary_search(vector<int> &arr,int n,int key)
{
    int l=0,r=n-1,comp=0;
    while(l<=r)
    {
        int mid=l+(r-l)/2;
        if(key==arr[mid])
        {
            break;
        }
        else if(key<arr[mid])
            r=mid-1;
        else
            l=mid+1;
        comp++;
    }
    if(l>r)
        cout<<"Not Present "<<comp<<endl;
    else
        cout<<"Present "<<comp+1<<endl;
}
int main()
{
    int t;
    cin>>t;
    while(t--)
    {
        int n;
        cin>>n;
        vector<int> arr(n);
        for(int &i:arr)
            cin>>i;
        int key;
        cin>>key;
        binary_search(arr,n,key);
    }
    return 0;
}
                                        
     
3-JUMP SEARCHING
  
  #include<bits/stdc++.h>
using namespace std;

int jumpSearch(int *a, int n, int key){
    int i=0,j=2;
    int comp=0;
    while(comp++ && a[j]<=key && j<n){
        if(a[j]==key){
            cout << "Present ";
            return j;
        }
        i=j;
        j*=2;
        if(j>=n){
            j=n-1;
        }
    }

    for(int k=i; k<=j; k++,comp++){
        if(a[k]==key){
            cout << "Present ";
            return j;
        }  
    }
    cout << "Not Present ";
    return comp;
}
int main(){
    int t;
    cin >> t;

    while(t--){
        int n;
        cin >> n;

        int *a=new int[n];
        for(int i=0;i<n;i++){
            cin >> a[i];
        }

        int key;
        cin >> key;

        cout << jumpSearch(a,n,key) << endl;
    }
    return 0;
}
