#include<bits/stdc++.h>
using namespace std;
int main()
{
    int t;
    cin>>t;
    while(t--){
        int n;
        cin>>n;
        int ar[n];
        vector<int>v;
        int pos=0,neg=0;
        for(int i=0; i<n; i++){
            cin>>ar[i];
            if(ar[i]>0) pos++;
            else if(ar[i]<0) neg++;
        }
        if(pos>2 || neg>2){
            cout<<"NO\n";
            continue;
        }
        else{
 
                bool flag=false;
            for(int i=0; i<n; i++){
                if(ar[i]!=0) v.push_back(ar[i]);
                if(ar[i]==0) flag=true;
            }
         if(flag) v.push_back(0);
            bool blck=true;
           for(int i=0; i<v.size(); i++){
               for(int j=0; j<v.size(); j++){
                  for(int k=0; k<v.size(); k++){
                      if(i!=j && i!=k && j!=k){
                          int x=v[i]+v[j]+v[k];
                          int m=0;
                          for(int ii=0; ii<v.size(); ii++){
                               if(v[ii]==x) m=1;
                          }
                          if(m!=1) blck=false;
                      }
                  }
               }
           }
           if(blck==false){
                cout<<"NO\n";
           }
           else cout<<"YES\n";
 
        }
    }
    return 0;
}
