# Inclass11
Bài tập trên lớp 11



#include <stdio.h>
#include <math.h>

bool kiemTraSNT(int number){
	if(number < 2){
        return false;
    }
    for(int i = 2; i <= sqrt(number); i++){
        if(number % i == 0){
            return false;
        }
    }
    return true;
}

void nhapMang(int arr[], int n){
	for (int i=0; i<n; i++){
		printf("arr[%d] = ", i);
		scanf("%d", &arr[i]);
	}
}

void xuatMang(int arr[], int n){
	printf("Xuat mang\n");
	for (int i=0; i<n; i++){
		printf("%d \t", arr[i]);
	}
	printf("\n");
}

void tinhTongSoChan(int arr[], int n){
	int sum = 0;
	for (int i=0; i<n; i++){
		if (arr[i]%2==0){
			sum += arr[i];
		}
	}
	printf("Tong cac so chan trong mang: %d\n", sum);
}

void demSoLe(int arr[], int n){
	int sum = 0;
	for (int i=0; i<n; i++){
		if (arr[i]%2!=0){
			sum ++;
		}
	}
	printf("Co %d so le trong mang\n", sum);
}

void demSNT(int arr[], int n){
	int count = 0;
	for (int i=0; i<n; i++){
		if (kiemTraSNT(arr[i])==true){
			count++;
		}
	}
	printf("Co %d so nguyen to trong mang\n", count);
}

bool kiemTraSoAm(int arr[], int n){
	for (int i=0; i<n; i++){
		if(arr[i] < 0){
			return true;
		}
	}
	return false;
}

int main(){
	int arr[100];
	int n = 0;
	printf("Nhap so phan tu mang: ");
	scanf("%d", &n);
	nhapMang(arr, n);
	xuatMang(arr, n);
	tinhTongSoChan(arr, n);
	demSoLe(arr, n);
	demSNT(arr, n);
	if (kiemTraSoAm(arr, n)){
		printf("Mang co so am");
	} else {
		printf("Mang k co so am");
	}
    return 0;
}
