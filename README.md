# covidspread

#include <bits/stdc++.h>
#include<vector>
using namespace std;

int main()
{
    long int T;
    cin>>T;
    while(T--)
    {
        int N;
        cin>>N;
        int A[N];
        for(int i=0;i<N;i++)
        {
            cin>>A[i];
        }
        int i=0,flag=1;
        while(i<N)
        {
            if(A[i]>A[i+1])
            {
                flag=0;break;
            }
            i++;
        }
        vector<int> C;
        for(int k=i;k<N;k++)
        {
            int count=0;
            for(int j=i;j<N;j++)
            {
                    if(abs(A[k]-A[j])==abs(j-k))
                    {
                        count++;   
                    }
            }
            C.push_back(count);
        }
        if(flag==0)
            cout<<*min_element(C.begin(),C.end())<<' '<<*max_element(C.begin(),C.end())<<endl;
        else
            cout<<1<<' '<<1<<endl;
    }
    return 0;
}
