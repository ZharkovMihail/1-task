# ip
#include<iostream>
using namespace std;
void main() {
	int n;
	cin >> n;
	int** a = new int*[n];
	for (int i = 0; i < n; ++i) {
		a[i] = new int[n];
		for (int j = 0; j < n; ++j) {
			a[i][j] = 0;
		}
	}

	int l;
	if (n % 2 == 0) {
		l = n / 2;
	}
	else {
		l = (n - 1) / 2;
		a[(n - 1) / 2][(n - 1) / 2] = n*n;
	}
	int k = 1;
	for (int p = 0; p < l; ++p) {
		for (int i = p; i < n-p; ++i) {
			a[i][p] = k;
			k++;
		}
		for (int i = p+1; i < n-p; ++i) {
			a[n-p-1][i] = k;
			k++;
		}
		for (int i = n-2-p; i >=p; --i) {
			a[i][n-p-1] = k;
			k++;
		}
		for (int i = n - 2 - p; i >= p+1; --i) {
			a[p][i] = k;
			k++;
		}
		
	}

	for (int i = 0; i < n; i++) {
		for (int j = 0; j < n; j++) {
			cout << a[i][j] << ' ';
		}
		cout << endl;
	}
	system("pause");
}
