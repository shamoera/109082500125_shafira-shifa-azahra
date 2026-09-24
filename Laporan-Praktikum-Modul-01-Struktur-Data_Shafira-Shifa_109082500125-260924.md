# <h1 align="center">Laporan Praktikum - Codeblocks IDE & Pengenalan Bahasa C++ (Bagian Pertama)</h1>
<p align="center">Shafira Shifa Azahra - 109082500125</p>

## Dasar Teori
Dalam bahasa C++, terdapat beberapa tipe data yang dapat digunakan untuk menyimpan nilai berupa angka. Contohnya adalah int yang digunakan untuk bilangan bulat dan float yang digunakan untuk bilangan desimal. C++ juga memiliki operator aritmatika seperti +, -, *, dan / yang dapat digunakan untuk melakukan perhitungan pada data numerik.

C++ juga memiliki struktur perulangan atau looping yang digunakan untuk menjalankan perintah secara berulang. Salah satu jenisnya adalah for, yang dapat digunakan untuk mengulang suatu proses berdasarkan kondisi atau jumlah pengulangan yang telah ditentukan. Perulangan for sering digunakan untuk membuat berbagai bentuk keluaran, seperti pola segitiga, tabel, dan pola cermin (mirror). Bentuk pola tersebut dapat diatur dengan menentukan jumlah baris, jumlah karakter, serta penggunaan spasi pada setiap baris.

### A. Operasi Aritmatika pada Tipe Data Float<br/>
Operasi aritmatika dasar (penjumlahan, pengurangan, perkalian, pembagian) dapat diterapkan langsung pada variabel bertipe `float` C++.
#### 1. Variabel bertipe float
#### 2. Input nilai menggunakan `cin`
#### 3. Operasi aritmatika dan output menggunakan `cout`

## Unguided

### 1. Program penjumlahan, pengurangan, perkalian, dan pembagian dua bilangan float

```C++
#include <iostream>
using namespace std;

int main() {
    float a, b;
    cout << "Masukkan bilangan pertama: ";
    cin >> a;
    cout << "Masukkan bilangan kedua  : ";
    cin >> b;

    cout << "Penjumlahan: " << a + b << endl;
    cout << "Pengurangan: " << a - b << endl;
    cout << "Perkalian  : " << a * b << endl;
    cout << "Pembagian  : " << a / b << endl;

    return 0;
}
```

### Output Unguided 1 :

![Screenshot Output Unguided 1](https://github.com/shamoera/109082500125_shafira-shifa-azahra/blob/main/modul01_soal1.png)

Hasil eksekusi program dengan input `7.5` dan `2.5`:
```
Masukkan bilangan pertama: 7.5
Masukkan bilangan kedua  : 2.5
Penjumlahan: 10
Pengurangan: 5
Perkalian  : 18.75
Pembagian  : 3
```

Program menerima dua buah bilangan bertipe `float` dari pengguna melalui `cin`, kemudian menghitung hasil penjumlahan, pengurangan, perkalian, dan pembagian menggunakan operator aritmatika bawaan C++, dan menampilkan keempat hasilnya melalui `cout`.

### 2. Program konversi angka (0-100) menjadi bentuk tulisan

```C++
#include <iostream>
#include <string>
using namespace std;

string satuan[] = {"nol","satu","dua","tiga","empat","lima","enam","tujuh","delapan","sembilan",
                    "sepuluh","sebelas","dua belas","tiga belas","empat belas","lima belas",
                    "enam belas","tujuh belas","delapan belas","sembilan belas"};
string puluhan[] = {"","","dua puluh","tiga puluh","empat puluh","lima puluh",
                     "enam puluh","tujuh puluh","delapan puluh","sembilan puluh"};

string terbilang(int n) {
    if (n == 100) {
        return "seratus";
    } else if (n < 20) {
        return satuan[n];
    } else {
        int sisa = n % 10;
        if (sisa == 0) return puluhan[n / 10];
        else return puluhan[n / 10] + " " + satuan[sisa];
    }
}

int main() {
    int angka;
    cout << "Masukkan angka (0-100): ";
    cin >> angka;

    cout << angka << " : " << terbilang(angka) << endl;

    return 0;
}
```

### Output Unguided 2 :

![Screenshot Output Unguided 2](https://github.com/shamoera/109082500125_shafira-shifa-azahra/blob/main/modul01_soal2.png)

Hasil eksekusi program :
```
Masukkan angka (0-100): 79 : tujuh puluh sembilan
Masukkan angka (0-100): 5 : lima
Masukkan angka (0-100): 100 : seratus
Masukkan angka (0-100): 30 : tiga puluh
```

Program menerima angka antara 0 sampai 100, kemudian memisahkannya menjadi nilai puluhan dan satuan. Setelah itu, nilai tersebut dicocokkan dengan isi array string `puluhan[]` dan `satuan[]` untuk menghasilkan bentuk angka dalam tulisan. 


### 3. Program pola cermin (mirror) berdasarkan angka input

```C++
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "input: ";
    cin >> n;
    cout << "output:" << endl;

    for (int j = 0; j <= n; j++) {
        int sisa = n - j;

        for (int s = 0; s < j; s++) cout << " ";

        for (int k = sisa; k >= 1; k--) cout << k;
        cout << "*";
        for (int k = 1; k <= sisa; k++) cout << k;

        cout << endl;
    }

    return 0;
}
```

### Output Unguided 3 :

![Screenshot Output Unguided 3](https://github.com/shamoera/109082500125_shafira-shifa-azahra/blob/main/modul01_soal3.png)

Hasil eksekusi program untuk input `3`:
```
input: 3
output:
321*123
 21*12
  1*1
   *
```

Program ini menggunakan perulangan `for` bersarang untuk membuat pola mirror. Perulangan `j` mengatur jumlah baris dan spasi di awal setiap baris, sedangkan variabel `sisa = n - j` menentukan jumlah tanda `*` yang dicetak di sisi kiri dan kanan. Jumlah `*` akan berkurang pada setiap baris hingga baris terakhir yang hanya menampilkan satu tanda `*`, sehingga membentuk pola seperti cermin.


## Kesimpulan
Berdasarkan ketiga latihan yang telah dilakukan, dapat disimpulkan bahwa C++ menyediakan operator aritmatika yang dapat digunakan secara langsung untuk melakukan perhitungan pada variabel bertipe `float`. Selain itu, array string dapat dimanfaatkan untuk mengubah angka menjadi bentuk tulisan atau terbilang. Penggunaan perulangan bersarang (*nested for loop*) juga dapat membantu dalam membuat berbagai pola keluaran berdasarkan baris dan kolom, salah satunya adalah pola mirror atau cermin.


## Referensi
[1] Tim Penyusun Praktikum Struktur Data. Modul 1: Code Blocks IDE & Pengenalan Bahasa C++ (Bagian Pertama). Purwokerto: Fakultas Informatika, Telkom University Purwokerto.
<br>