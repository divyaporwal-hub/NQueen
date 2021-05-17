# NQueen
This is the backtracking problem..
#include<bits/stdc++.h>

using namespace std;

#define send {ios_base::sync_with_stdio(false);}

#define help {cin.tie(NULL);}

#define int               long long int

#define rep(i,a,b)        for(int i=a;i<b;i++)

char arr[1000][1000];

bool ispossible(int row, int col, int size){

       

        for(int i = row,j = col; i >=0 && j >=0; i--){

              if(arr[i][j] == 'Q'){

                  return false;

              }

        }

        for(int i = row,j = col; i >=0 && j >=0; i--,j++){

              if(arr[i][j] == 'Q'){

                  return false;

              }

        }

        for(int i = row,j = col; i >=0 && j >=0; i--, j--){

              if(arr[i][j] == 'Q'){

                 return false;

              }

        }

    return true;

}

void queenshelp(int row,int size){

       if(row == size){

            for(int i = 0; i < size; i++){

                 for(int j = 0; j < size; j++){

                     cout << arr[i][j] << " ";

                 }

                 cout << '\n';

            }

            cout << '\n';

            return;

       }

       for(int j = 0; j < size; j++){

           if(ispossible(row,j,size)){

               arr[row][j] = 'Q';

               queenshelp(row+1,size);

               arr[row][j] = '_';

           }

       }

    return;

}

void queens(int n){

     queenshelp(0,n);

}

void solve(){

    int n;

    cin >> n;

    for(int i = 0; i < 1000; i++){

     for(int j = 0; j < 1000; j++){

         arr[i][j] = '_';

     }

    }

    queens(n);

}

signed main(){

       send help 

       // int tc;

       // cin >> tc;

       // while(tc--){

          solve();

       // }

}
