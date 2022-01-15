# yenngua
yenngua
#include<iostream>
using namespace std;
int kiemtracot(int a[100][100], int m, int i, int maxhang){
	int maxcot= a[0][i];
	for (int j=0; j< m ; j++){
		if (maxcot > a[j][i]){
			maxcot = a[j][i];
		}	
	} if (maxcot == maxhang) return 1;
	return 0;
}
void kiemtraphantu(int a[100][100], int m, int n ){
	for (int i=0; i< m ; i++){
		int maxhang=a[i][0];
		for (int j=1; j < n ; j++){
			if (maxhang<a[i][j]) maxhang = a[i][j];
		}
		for (int j=0; j < n ; j++){
			if (maxhang==a[i][j]){
				if (kiemtracot(a,m,j,maxhang)){
					cout << i+1 <<  " " << j+1 << endl;
				} 
			}
		}
	}
}

int kiemtrasoluong(int a[100][100], int m, int n){
	int k=0;
	for (int i=0; i< m ; i++){
		int maxhang=a[i][0];
		for (int j=1; j < n ; j++){
			if (maxhang<a[i][j]) maxhang = a[i][j];
		}
		for (int j=0; j < n ; j++){
			if (maxhang==a[i][j]){
				if (kiemtracot(a,m,j,maxhang)){
					k++;
				} 
			}
		}
	}
	return  k;
}
int main(){
	int m,n;
	int a[100][100];
	cin >> m >> n;
	for (int i=0; i< m ; i++){
		for (int j=0; j < n ; j++){
			cin >> a[i][j];
		}
	}
	cout << kiemtrasoluong(a,m,n) << endl;
	kiemtraphantu(a,m,n);
	
	
	
	
	return 0;
}
