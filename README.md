// Nama Anggota :
// Kerina Bakarudin, NPM : 2217051027
// Lira Septiyani, NPM : 2217051151
// Reffa Hibatullah, NPM : 2217051157

#include <iostream>
#include <conio.h>
#include <stdlib.h>
#include <stdio.h>
using namespace std;

#define gopay 0.02
#define dana 0.02
#define bca 0.04
#define bri 0.04
#define mandiri 0.04
#define tidak_diketahui 0.08 

#define discount0 0.00
#define discount1 0.10
#define discount2 0.15
#define discount3 0.20
#define discount4 0.25
#define discount5 0.30

void header(){
	cout<<"===============================================================================================" <<endl;
	cout<<"==================================    SELAMAT DATANG DI   =====================================" <<endl;
	cout<<"==================================       RKL BAKERY       =====================================" <<endl;
	cout<<"==================================  JUAL MACAM-MACAM KUE  =====================================" <<endl;
	cout<<"===============================================================================================" <<endl;
}
 
void footer(){
	cout<<"====================   TERIMA KASIH ATAS PEMBELIANNYA   ====================" <<endl;
	cout<<"====================   DITUNGGU KEDATANGAN NYA KEMBALI  ====================";
}
int program(){
	string nama, nomor_hp, alamat, pembayaran, pilihan1, pilihan2, pilihan3;
	char kembali;
	int pesan[3], pesanan, jarak, jumlah_kue, pajak, diskon, ongkir, total, total_akhir, bayar, kurang, sisa_pembayaran, kembalian;
	int harga[15] = {150000, 120000, 100000, 80000, 70000, 115000, 50000, 30000, 50000, 20000, 130000, 100000, 80000, 85000, 85000}, h1 = 0, h2 = 0, h3 = 0;
	bool tunai;
		
		do{
		system("CLS");
		system("Color 40");
		header();
		cout<<endl;
		cout<<" RKL Bakery adalah Toko yang menjual berbagai macam kue dan roti dari berbagai varian rasa." <<endl;
		cout<<" Jl. Prof. Dr. Ir. Sumantri Brojonegoro No.1, Gedong Meneng, Bandar Lampung, Lampung." <<endl;
		cout<<" No. Handphone/Whatsapp      : 083178636773 " <<endl;
		cout<<" Menerima Pembayaran Melalui : GOPAY, DANA, BCA, BRI, DAN MANDIRI." <<endl;
		cout<<" Melayani Hingga Jarak       : 15 Km." <<endl;
		cout<<endl;
		cout<<"                          PROMO DISKON                                 " <<endl;
		cout<<" 1) Pembelian Rp. 50000 - Rp. 100000, Mendapatkan Diskon 10%           " <<endl;
		cout<<" 2) Pembelian Rp. 100000 - Dibawah Rp.200000, Mendapatkan Diskon 15%   " <<endl;
		cout<<" 3) Pembelian Rp. 200000 - Dibawah Rp.300000, Mendapatkan Diskon 20%   " <<endl;
		cout<<" 4) Pembelian Rp. 300000 - Dibawah Rp.400000, Mendapatkan Diskon 25%   " <<endl;
		cout<<" 5) Pembelian Diatas Rp. 400000, Mendapatkan Diskon 30%                " <<endl;
		cout<<endl;
		cout<<"Berikut List Menu Kami : " <<endl;
		cout<<"---------------------------------------------------------------------------------" <<endl;
		cout<<"-------------------------    LIST MACAM KUE DAN ROTI    -------------------------" <<endl;
		cout<<"---------------------------------------------------------------------------------" <<endl;
		cout<<"-             1)  Tart Cake                  = Rp. 150.000                      -" <<endl;
		cout<<"-             2)  Cheese Cake                = Rp. 120.000                      -" <<endl;
		cout<<"-             3)  Choco Cake                 = Rp. 100.000                      -" <<endl;
		cout<<"-             4)  Strawberries Cake          = Rp. 80.000                       -" <<endl;
		cout<<"-             5)  Rainbow Cake               = Rp. 70.000                       -" <<endl;
		cout<<"-             6)  Red Velvet Cake            = Rp. 115.000                      -" <<endl;   
		cout<<"-             7)  Brownies                   = Rp. 50.000                       -" <<endl; 
		cout<<"-             8)  Muffin                     = Rp. 30.000                       -" <<endl; 
		cout<<"-             9)  Cloud Bread                = Rp. 50.000                       -" <<endl; 
		cout<<"-             10) Sandwich                   = Rp. 20.000                       -" <<endl;
		cout<<"-             11) Crocodile Bread            = Rp. 130.000                      -" <<endl;
		cout<<"-             12) Pizza                      = Rp. 100.000                      -" <<endl;    
		cout<<"-             13) Tiramisu Cake              = Rp. 80.000                       -" <<endl;
		cout<<"-             14) Oreo Cake                  = Rp. 85.000                       -" <<endl;
		cout<<"-             15) Matcha Cake                = Rp. 85.000                       -" <<endl;                                   
		cout<<"---------------------------------------------------------------------------------" <<endl;
		cout<<endl;
		cout<<" JIka Ingin Memesan Dapat Langsung Pilih List Di Atas dan Isi :" <<endl;
		string ignore;cout<<" (Tekan Enter Untuk Mengisi) "; getline(cin,ignore); cout<<endl;
		cout<<" Nama Lengkap                  : "; getline(cin,nama); 
		cout<<" No. Handphone                 : "; getline(cin,nomor_hp); 
		cout<<" Alamat Pengiriman             : "; getline(cin,alamat); 
		cout<<" Metode Pembayaran             : "; getline(cin,pembayaran);
		cout<<" Jarak Pengiriman (Maks 15 Km) : "; cin>>jarak;
		
		if(jarak >= 0 && jarak <=3){
			ongkir = 0;
		}
		else if(jarak > 3 && jarak <= 7){
			ongkir = 10000;
		}
		else if(jarak > 7 && jarak <= 10 ){
			ongkir = 15000;	
		}
		else if(jarak > 10 && jarak <= 15){
			ongkir = 20000;
		}
		else{
			cout<<" Maaf, Kami Tidak Melayani Pengiriman Dengan Jarak Lebih dari 15 Km" <<endl;
			goto awal;
		}
		
 		cout<<" Jumlah Yang Dipesan (Maks 3)  : "; cin>>jumlah_kue;
 		if(jumlah_kue == 1){
			cout<<" Kue Yang Di Pesan             : No. "; cin>>pesan[0];
		}
		else if(jumlah_kue == 2){
			cout<<" Kue ke-1 Yang Di Pesan        : No. "; cin>>pesan[0];
			cout<<" Kue ke-2 Yang Di Pesan        : No. "; cin>>pesan[1];
		}
		else if(jumlah_kue == 3){	
			cout<<" Kue ke-1 Yang Di Pesan        : No. "; cin>>pesan[0];
			cout<<" Kue ke-2 Yang Di Pesan        : No. "; cin>>pesan[1];		
			cout<<" Kue ke-3 Yang Di Pesan        : No. "; cin>>pesan[2];
		}
		else{
			cout<<" Maaf, Anda Memesan Dari Batas Maksimal";
			goto awal;
		}
		
		switch(pesan[0]){
			case 1:
				(pilihan1 = "Tart Cake");
				h1 = 0;
				break;
			case 2:
				(pilihan1 = "Cheese Cake");
				h1 = 1;
				break;				
			case 3:
				(pilihan1 = "Choco Cake");
				h1 = 2;
				break;
			case 4:
				(pilihan1 = "Strawberries Cake");
				h1 = 3;
				break;
			case 5:
				(pilihan1 = "Rainbow Cake");
				h1 = 4;
				break;
			case 6:
				(pilihan1 = "Red Velvet Cake");
				h1 = 5;
				break;
			case 7:
				(pilihan1 = "Brownies");
				h1 = 6;
				break;
			case 8:
				(pilihan1 = "Muffin");
				h1 = 7;
				break;
			case 9:
				(pilihan1 = "Cloud Bread");
				h1 = 8;
				break;
			case 10:
				(pilihan1 = "Sandwich");
				h1 = 9;
				break;
			case 11:
				(pilihan1 = "Crocodile Bread");
				h1 = 10;
				break;
			case 12:
				(pilihan1 = "Pizza");
				h1 = 11;
				break;
			case 13:
				(pilihan1 = "Tiramisu Cake");
				h1 = 12;
				break;
			case 14:
				(pilihan1 = "Oreo Cake");
				h1 = 13;
				break;
			case 15:
				(pilihan1 = "Matcha Cake");
				h1 = 14;
				break;			
			default:
				(pilihan1 = " Maaf Pilihan Anda Tidak Tersedia");
		}
		
		
		switch(pesan[1]){
			case 1:
				(pilihan2 = "Tart Cake");
				h2 = 0;
				break;
			case 2:
				(pilihan2 = "Cheese Cake");
				h2 = 1;
				break;				
			case 3:
				(pilihan2 = "Choco Cake");
				h2 = 2;
				break;
			case 4:
				(pilihan2 = "Strawberries Cake");
				h2 = 3;
				break;
			case 5:
				(pilihan2 = "Rainbow Cake");
				h2 = 4;
				break;
			case 6:
				(pilihan2 = "Red Velvet Cake");
				h2 = 5;
				break;
			case 7:
				(pilihan2 = "Brownies");
				h2 = 6;
				break;
			case 8:
				(pilihan2 = "Muffin");
				h2 = 7;
				break;
			case 9:
				(pilihan2 = "Cloud Bread");
				h2 = 8;
				break;
			case 10:
				(pilihan2 = "Sandwich");
				h2 = 9;
				break;
			case 11:
				(pilihan2 = "Crocodile Bread");
				h2 = 10;
				break;
			case 12:
				(pilihan2 = "Pizza");
				h2 = 11;
				break;
			case 13:
				(pilihan2 = "Tiramisu Cake");
				h2 = 12;
				break;
			case 14:
				(pilihan2 = "Oreo Cake");
				h2 = 13;
				break;
			case 15:
				(pilihan2 = "Matcha Cake");
				h2 = 14;
				break;			
			default:
				( pilihan2 = "Maaf Pilihan Anda Tidak Tersedia" );				
		}
		
		
		switch(pesan[2]){
			case 1:
				(pilihan3 = "Tart Cake");
				h3 = 0;
				break;
			case 2:
				(pilihan3 = "Cheese Cake");
				h3 = 1;
				break;				
			case 3:
				(pilihan3 = "Choco Cake");
				h3 = 2;
				break;
			case 4:
				(pilihan3 = "Strawberries Cake");
				h3 = 3;
				break;
			case 5:
				(pilihan3 = "Rainbow Cake");
				h3 = 4;
				break;
			case 6:
				(pilihan3 = "Red Velvet Cake");
				h3 = 5;
				break;
			case 7:
				(pilihan3 = "Brownies");
				h3 = 6;
				break;
			case 8:
				(pilihan3 = "Muffin");
				h3 = 7;
				break;
			case 9:
				(pilihan3 = "Cloud Bread");
				h3 = 8;
				break;
			case 10:
				(pilihan3 = "Sandwich");
				h3 = 9;
				break;
			case 11:
				(pilihan3 = "Crocodile Bread");
				h3 = 10;
				break;
			case 12:
				(pilihan3 = "Pizza");
				h3 = 11;
				break;
			case 13:
				(pilihan3 = "Tiramisu Cake");
				h3 = 12;
				break;
			case 14:
				(pilihan3 = "Oreo Cake");
				h3 = 13;
				break;
			case 15:
				(pilihan3 = "Matcha Cake");
				h3 = 14;
				break;			
			default:
				(pilihan3 = "Maaf Pilihan Anda Tidak Tersedia");
		}
			
			
		cout<<endl;
		
		if(jumlah_kue == 1){
			cout<<">>>>> Anda Memilih " <<pilihan1 <<" Sebagai Pesanan Anda <<<<<" <<endl;
		}
		else if(jumlah_kue == 2){
		  cout<<">>>>> Anda Memilih " <<pilihan1 <<" dan " <<pilihan2 <<" Sebagai Pesanan Anda <<<<<" <<endl;
		}
		else if(jumlah_kue == 3){
			cout<<">>>>> Anda Memilih " <<pilihan1 <<" , " <<pilihan2 <<" dan " <<pilihan3 <<" Sebagai Pesanan Anda <<<<<" <<endl;
		}
		
		getch();
		cout<<endl;
		
		system("CLS");
		system(" Color 30");
		cout<<" Berikut Struk Pembayaran Anda : " <<endl;
		
		if(jumlah_kue == 1){
			pesanan = harga[h1];
		}
		else if(jumlah_kue == 2){
			pesanan = harga[h1] + harga[h2];
		}
		else if(jumlah_kue == 3){
			pesanan = harga[h1] + harga[h2] + harga[h3];	
		}
		
		cout<<"______________________________________________________________________________"<<endl;
		cout<<" Nama Pembeli      : " <<nama <<endl; 
		
		if(jumlah_kue == 1){
			cout<<" Pesanan           : " <<pilihan1 <<endl;
		}
		else if(jumlah_kue == 2){
			if(pesan[0] == 1 && pesan[1] == 1){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else if(pesan[0] == 2 && pesan[1] == 2){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else if(pesan[0] == 3 && pesan[1] == 3){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else if(pesan[0] == 4 && pesan[1] == 4){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else if(pesan[0] == 5 && pesan[1] == 5){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else if(pesan[0] == 6 && pesan[1] == 6){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else if(pesan[0] == 7 && pesan[1] == 7){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else if(pesan[0] == 8 && pesan[1] == 8){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else if(pesan[0] == 9 && pesan[1] == 9){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else if(pesan[0] == 10 && pesan[1] == 10){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else if(pesan[0] == 11 && pesan[1] == 11){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else if(pesan[0] == 12 && pesan[1] == 12){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else if(pesan[0] == 13 && pesan[1] == 13){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else if(pesan[0] == 14 && pesan[1] == 14){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else if(pesan[0] == 15 && pesan[1] == 15){
			cout<<" Pesanan           : 2 " <<pilihan2 <<endl;
			}
			else{
		    cout<<" Pesanan           : " <<pilihan1 <<" dan " <<pilihan2 <<endl;
			}
		}
		else if(jumlah_kue == 3){
			if(pesan[0] == 1 && pesan[1] == 1 && pesan[2] == 1){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else if(pesan[0] == 2 && pesan[1] == 2  && pesan[2] == 2){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else if(pesan[0] == 3 && pesan[1] == 3 && pesan[2] == 3){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else if(pesan[0] == 4 && pesan[1] == 4  && pesan[2] == 4){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else if(pesan[0] == 5 && pesan[1] == 5  && pesan[2] == 5){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else if(pesan[0] == 6 && pesan[1] == 6  && pesan[2] == 6){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else if(pesan[0] == 7 && pesan[1] == 7  && pesan[2] == 7){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else if(pesan[0] == 8 && pesan[1] == 8  && pesan[2] == 8){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else if(pesan[0] == 9 && pesan[1] == 9  && pesan[2] == 9){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else if(pesan[0] == 10 && pesan[1] == 10  && pesan[2] == 10){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else if(pesan[0] == 11 && pesan[1] == 11  && pesan[2] == 11){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else if(pesan[0] == 12 && pesan[1] == 12  && pesan[2] == 12){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else if(pesan[0] == 13 && pesan[1] == 13  && pesan[2] == 13){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else if(pesan[0] == 14 && pesan[1] == 14  && pesan[2] == 14){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else if(pesan[0] == 15 && pesan[1] == 15  && pesan[2] == 15){
			cout<<" Pesanan           : 3 " <<pilihan3 <<endl;
			}
			else{
			cout<<" Pesanan           : " <<pilihan1 <<" , " <<pilihan2 <<" dan " <<pilihan3 <<endl;
			}
		}
		
		
		if(pesanan >= 0 && pesanan < 50000){
			diskon = pesanan * discount0;
		}
		else if(pesanan >= 50000 && pesanan < 100000){
			diskon = pesanan * discount1;
		}
		else if(pesanan >= 100000 && pesanan < 200000){
			diskon = pesanan * discount2;
		}
		else if(pesanan >= 200000 && pesanan < 300000){
			diskon = pesanan * discount3;
		}
		else if(pesanan >= 300000 && pesanan < 400000){
			diskon = pesanan * discount4;
		}
		else{
			diskon = pesanan * discount5;
		}
		
		
		total = pesanan - diskon;
		cout<<" Alamat Pengiriman : " <<alamat <<endl;
		cout<<" Metode Pembayaran : " <<pembayaran <<endl;
		cout<<" Jarak Pengiriman  : " <<jarak <<" Km" <<endl;
		cout<<"______________________________________________________________________________" <<endl;
		cout<<" Harga             : Rp. " <<pesanan <<endl;
		cout<<" Harga Diskon      : Rp. " <<diskon <<endl;
		cout<<"                     --------- -" <<endl;
		cout<<" Total             : Rp. " <<total <<endl;
		
		
		if(pembayaran == "GOPAY" || pembayaran == "gopay"){
			pajak = total * gopay;
		}
		else if(pembayaran == "DANA" || pembayaran == "dana"){
			pajak = total * dana;
		}
		else if(pembayaran == "BCA" || pembayaran == "bca"){
			pajak = total * bca;
		}
		else if(pembayaran == "BRI" || pembayaran == "bri"){
			pajak = total * bri;
		}
		else if(pembayaran == "MANDIRI" || pembayaran == "mandiri"){
			pajak = total * mandiri;
		}
		else{
			pajak = total * tidak_diketahui;
		}
		
		
		total_akhir = total + pajak + ongkir;
		cout<<" Pajak             : Rp. " <<pajak <<endl;
		cout<<" Ongkis Kirim      : Rp. " <<ongkir <<endl;
		cout<<"                     --------- +" <<endl;
		cout<<" Total Akhir       : Rp. " <<total_akhir <<endl;
		cout<<"______________________________________________________________________________" <<endl;
		cout<<endl;
		cout<<endl;
		cout<<"---------------------------------------" <<endl;
		cout<<" Silahkan Untuk Membayar Disini : " <<endl;
		cout<<" Masukkan Uang Rp. "; cin>>bayar; cout<<endl;

		do{
			if(tunai = bayar < total_akhir){
			sisa_pembayaran = total_akhir - bayar;
			cout<<" Mohon Maaf Uang Anda Kurang Rp. " <<sisa_pembayaran <<", Silahkan Untuk Menambah Pembayaran Anda : Rp. " ; cin>>kurang; cout<<endl;
			bayar = bayar + kurang;
			}	  
		}
		while(tunai = bayar < total_akhir);
		
		cout<<endl;
		cout<<"---------------------------------------" <<endl;
		if(tunai = bayar  > total_akhir){
			kembalian = bayar - total_akhir;
			cout<<" Anda Membayar Sebesar Rp. " <<bayar <<endl;
			cout<<" Ini Uang Kembalian Anda Rp. " <<kembalian <<endl;
		}
		else if(tunai = bayar == total_akhir){
			cout<<" Anda Membayar Sebesar Rp. " <<bayar <<endl;
			cout<<" Uang Anda Pas" <<endl;
		}
		
		cout<<endl;
		
		awal:
			cout<<" Apakah Anda Ingin Memesan Kembali ?" <<endl;
			cout<<" [Y/N] " ; cin>>kembali;
	}while(kembali == 'Y' || kembali == 'y');

	cout<<endl;	
	footer();
}

int main(){
	program();

	getch();
	return 0;
}
