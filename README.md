#include <iostream>
using namespace std;
void Hoanvi(double &x, double &y){
    double temp = x;
    x = y;
    y = temp;
}
void SosanhHoanvi(double a[], int &n){	
    for (int i = 0; i < n - 1; i++)
        for (int j = i + 1; j <n; j++)
	        if(a[i] > a[j])  
		        Hoanvi(a[i], a[j]);
}
int main(){
    int n;
    int tu,mau;
    cout<<"nhap n:";
    cin>>n;
    double giatri,a[n];
    double tong=0.0;
    for(int i=0;i<=n-1;i++){
        cout<<"Nhap phan tu a["<<i<<"]:";
        cin>>tu;
        cout<<"/";
        cin>>mau;
        giatri=(double)tu/mau;
        a[i]=giatri;
        tong+=giatri;
    }
    cout<<"Tong cua day: "<<tong<<" \n";
    for(int k=0;k<=n-1;k++){
        SosanhHoanvi(a,n);
        cout<<a[k]<<" ";
    }
    return 0;
}
