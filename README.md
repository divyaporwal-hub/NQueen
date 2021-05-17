# NQueen
This is the backtracking problem..
#include<iostream>
#define int long long int 
#define rep(i,n) for(int i=0;i<n;i++)
#define rep1(i,n) for(int i=1;i<=n;i++)
char arr[1000][1000];
using namespace std;
bool issafe(int row ,int col, int n)
{
    for(int i=row;i>=0;i--)
    {
        if(arr[i][col]=='Q')
        return false;
        
    }
    for(int i=row,j=col;i>=0&&j>=0;i--,j--)
    {
        if(arr[i][j]=='Q')
        return false;
    }
    for(int i=row,j=col;i>=0&&j>=0;i--,j++)
    {
        if(arr[i][j]=='Q')
        return false;
        
    }
    return true;
}
void queen(int row,int n)
{
    if(row==n)
    {
           rep(i,n){
    rep(j,n)
    cout<<arr[i][j]<<".";
    cout<<'\n';
    } cout<<'\n';
        return;
    }
    rep(j,n)
    {
        if(issafe(row,j,n)){
        arr[row][j]='Q';
        queen(row+1,n);
        arr[row][j]='.';
        }
    }
    return;
        
}
signed main()    
{ int n;
  cin>>n;
  rep(i,n)
  rep(j,n)
  arr[i][j]='.';
  queen(0,n) ;
    
    return 0;
}
