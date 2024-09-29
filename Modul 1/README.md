# Praktikum-IPSD-Assignment
# <h1 align="center">Laporan Praktikum Modul Dasar-Dasar Python untuk Sains Data</h1>
<p align="center">Ratih Ambara Sukma Kurnilia</p>

## Dasar Teori

## A. Variable & Tipe Data
Variabel adalah tempat menyimpan data di memori. Nama variabel harus mengikuti aturan penamaan. Menggunakan huruf, angka, atau underscore (_), dan tidak boleh diawali dengan angka. Python mendukung beberapa tipe data dasar, antara lain:

1) Integer (int) : 10, -3
   
2) Float : 3.14, -2.5
   
3) String (str) : Data Science

4) Boolean (bool) : True/ False

## B. Operator & Logika
Jenis operator yang sering digunakan di Python :

1. Operator Aritmatika : +, -, *, / (operasi dasar), // (pembagian bulat), % (modulo), ** (eksponensial)
2. Operator Perbandingan, hasilnya (True/ False) : == (sama dengan), != (tidak sama dengan), >, <, >=, <= (perbandingan nilai besar dan kecil)
3. Operator Logika : and (bernilai True jika kedua operand bernilai True), or (bernilai True jika salah satu operand bernilai True), not (membalik nilai boolean)

## C. Fungsi, Pengulangan & Percabangan
Fungsi menggunakan def diikuti nama fungsi. Macam-macam pengulangan :
1. For Loop : mengiterasi item dalam list, tuple, dictionary, atau range.
2. While Loop : terus berjalan selama suatu kondisi terpenuhi.
3. List Comprehension : menulis loop yang menghasilkan list.

Percabangan digunakan untuk pengambilan suatu keputusan berdasarkan kondisi. Biasanya menggunakan If, Elif, Else. Terdapat istilah Nested Conditionals yaitu percabangan bersarang.

## Guided 

### 1. Variable & Tipe Data

```
# Variable dan Tipe Data
x = 10
y = 3.14
z = "Data Science"

user_age = 20
pi_value = 3.14159
course_name = "Python for Data Science"

# Integers
age = 25

# Floats
height = 1.75

# Strings
name = "Ratih"

#Booleans
is_student = True

print (type(age))
print (type(height))
print (type(name))
print (type(is_student))
```

### 2. Operator & Logika

```
# Operator Aritmatika
a = 10
b = 3

# Penjumlahan
print(a + b)

# Pembagian
print(a / b)

# Pembagian Bulat
print(a // b)

# Eksponensial
print(a ** b)

# Operator Perbandingan
print(a > b) #Output: True
print(a == b) #Output: False

# Operator Logika
x = True
y = False
print(x and y)
print(x or y)
```

### 3. Fungsi, Pengulangan & Percabangan

```
# Pengulangan
# For Loop
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)

# While Loop
counter = 0
while counter < 3:
    print(counter)
    counter += 1

# List Comprehension
numbers = [1, 2, 3, 4, 5]
double = [x * 2 for x in numbers]

# If, Elif, Else
score = 85
if score >= 90:
    print("A")
elif score >= 80:
    print("B")
else:
    print("C")

# Nested Conditionals
score = 85
attendance = 90
if score >= 80:
    if attendance >= 85:
        print("Lulus dengan nilai baik")
    else:
        print("Kehadiran kurang")
else:
    print("Tidak lulus")
```

## Unguided 

### 1. Buatlah program yang dapat menghasilkan pola berbentuk angka seperti di bawah ini, dengan syarat angka yang ditampilkan adalah hasil dari penjumlahan bilangan prima sebelumnya. Jumlah angka pada setiap baris bertambah 1, dan bilangan yang ditampilkan adalah bilangan prima.

```
def adalah_prima(n):
    if n <= 1:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

def buat_pola_prima(baris):
    prima = []
    angka = 2
    for i in range(1, baris + 1):
        baris_prima = []
        while len(baris_prima) < i:
            if adalah_prima(angka):
                baris_prima.append(angka)
            angka += 1
        prima.append(baris_prima)

    for baris_prima in prima:
        print(" ".join(map(str, baris_prima)))

buat_pola_prima(4)
```
#### Output:
![Screenshot 2024-04-26 105533](https://github.com/ratihambara/Praktikum-Struktur-Data-Assignment/assets/161399790/dad85963-58eb-4491-a52f-8a8f8f9dd9fe)

Fungsi adalah_prima(n) digunakan untuk memeriksa apakah suatu bilangan adalah bilangan prima. Fungsi buat_pola_prima(baris) menggunakan loop untuk setiap baris dan menambahkan bilangan prima yang sesuai.

### 2.   Buatlah sebuah fungsi yang menerima dua input berupa list angka. Fungsi ini harus mengembalikan sebuah list baru yang berisi elemen dari dua list input yang memiliki indeks ganjil. List baru tersebut juga harus diurutkan secara menurun berdasarkan nilai elemen.

```
def gabung_urut_ganjil(list1, list2):
    # Mengambil elemen dengan indeks ganjil dari kedua list
    elemen_ganjil = [list1[i] for i in range(1, len(list1), 2)] + [list2[i] for i in range(1, len(list2), 2)]
    
    # Mengurutkan elemen secara menurun
    elemen_ganjil.sort(reverse=True)
    
    return elemen_ganjil

list1 = [10, 21, 32, 43, 54]
list2 = [65, 76, 87, 98, 109]
hasil = gabung_urut_ganjil(list1, list2)
print(hasil)
```
#### Output:
![Screenshot 2024-04-26 105728](https://github.com/ratihambara/Praktikum-Struktur-Data-Assignment/assets/161399790/df6bd4d8-813d-4627-976d-c28002973985)

Fungsi gabung_urut_ganjil menerima dua list sebagai input. Menggunakan list comprehension untuk mengambil elemen dengan indeks ganjil dari kedua list. Menggabungkan elemen-elemen tersebut dan mengurutkannya secara menurun menggunakan sort(reverse=True)

### 3.   Buat sebuah program untuk mensimulasikan transaksi ATM. Program harus:
1. Meminta pengguna memasukkan PIN (dibatasi 3 kali percobaan).
2. Setelah PIN benar, meminta jumlah penarikan.
3. Jika saldo kurang dari jumlah yang ditarik, munculkan pesan kesalahan.
4. Jika penarikan berhasil, tampilkan saldo akhir.

```
def atm_simulasi():
    saldo = 1000000  # Saldo awal
    pin_benar = "1234"  # PIN yang benar
    percobaan = 0

    # Meminta pengguna memasukkan PIN (dibatasi 3 kali percobaan)
    while percobaan < 3:
        pin = input("Masukkan PIN Anda: ")
        if pin == pin_benar:
            break
        else:
            percobaan += 1
            print(f"PIN salah. Percobaan {percobaan} dari 3.")
    else:
        print("Anda telah memasukkan PIN yang salah sebanyak 3 kali. Kartu ATM Anda diblokir.")
        return

    # Meminta jumlah penarikan
    try:
        jumlah_tarik = int(input("Masukkan jumlah penarikan: "))
    except ValueError:
        print("Jumlah penarikan harus berupa angka.")
        return

    # Memeriksa apakah saldo cukup
    if jumlah_tarik > saldo:
        print("Saldo tidak mencukupi untuk penarikan ini.")
    else:
        saldo -= jumlah_tarik
        print(f"Penarikan berhasil. Saldo akhir Anda adalah: Rp{saldo}")

# Menjalankan simulasi ATM
atm_simulasi()
```
#### Output:
![Screenshot 2024-04-26 105728](https://github.com/ratihambara/Praktikum-Struktur-Data-Assignment/assets/161399790/df6bd4d8-813d-4627-976d-c28002973985)

Program memeriksa apakah saldo cukup untuk penarikan. Jika tidak cukup, muncul pesan kesalahan. Jika cukup, saldo dikurangi dengan jumlah penarikan dan saldo akhir ditampilkan.

### 4. Anda diberikan file CSV berisi data nilai ujian mahasiswa. Tugas Anda adalah menulis sebuah program yang:
1. Membaca file CSV dan menyimpan datanya ke dalam dictionary.
2. Menghitung rata-rata nilai tiap mahasiswa.
3. Menampilkan mahasiswa dengan nilai tertinggi dan terendah.

```
import pandas as pd
import numpy as np
import csv

def baca_csv(nilai_siswa):
    data_mahasiswa = {}
    with open(nilai_siswa, mode='r') as file:
        csv_reader = csv.reader(file)
        header = next(csv_reader)  # Membaca header
        for row in csv_reader:
            nama = row[0]
            nilai = list(map(int, row[1:]))
            data_mahasiswa[nama] = nilai
    return data_mahasiswa

def hitung_rata_rata(data_mahasiswa):
    rata_rata = {}
    for nama, nilai in data_mahasiswa.items():
        rata_rata[nama] = sum(nilai) / len(nilai)
    return rata_rata

def tampilkan_tertinggi_terendah(rata_rata):
    tertinggi = max(rata_rata, key=rata_rata.get)
    terendah = min(rata_rata, key=rata_rata.get)
    print(f"Mahasiswa dengan nilai tertinggi: {tertinggi} dengan rata-rata nilai {rata_rata[tertinggi]:.2f}")
    print(f"Mahasiswa dengan nilai terendah: {terendah} dengan rata-rata nilai {rata_rata[terendah]:.2f}")

nilai_siswa = 'nilai_siswa.csv'  
data_mahasiswa = baca_csv(nilai_siswa)
rata_rata = hitung_rata_rata(data_mahasiswa)
tampilkan_tertinggi_terendah(rata_rata)
```
#### Output:
![Screenshot 2024-04-26 105728](https://github.com/ratihambara/Praktikum-Struktur-Data-Assignment/assets/161399790/df6bd4d8-813d-4627-976d-c28002973985)

Fungsi hitung_rata_rata(data_mahasiswa) menghitung rata-rata nilai tiap mahasiswa dan mengembalikan dictionary dengan nama mahasiswa sebagai kunci dan rata-rata nilai sebagai nilai.

### 5. Buatlah permainan sederhana menggunakan Python, di mana komputer akan memilih sebuah angka secara acak antara 1 hingga 100, dan pengguna harus menebak angka tersebut. Setiap tebakan yang salah akan memberikan petunjuk apakah angka yang ditebak lebih besar atau lebih kecil dari angka sebenarnya. Batasi jumlah percobaan menjadi 5 kali. Setelah permainan selesai, tampilkan apakah pemain menang atau kalah.

```
import random

def permainan_tebak_angka():
    angka_rahasia = random.randint(1, 100)
    percobaan = 0
    max_percobaan = 5

    print("Selamat datang di permainan tebak angka!")
    print("Saya telah memilih sebuah angka antara 1 hingga 100.")
    print(f"Anda memiliki {max_percobaan} kali percobaan untuk menebak angka tersebut.")

    while percobaan < max_percobaan:
        try:
            tebakan = int(input("Masukkan tebakan Anda: "))
        except ValueError:
            print("Masukkan angka yang valid.")
            continue

        percobaan += 1

        if tebakan < angka_rahasia:
            print("Terlalu kecil!")
        elif tebakan > angka_rahasia:
            print("Terlalu besar!")
        else:
            print(f"Selamat! Anda berhasil menebak angka {angka_rahasia} dalam {percobaan} percobaan.")
            return

    print(f"Maaf, Anda telah kehabisan percobaan. Angka yang benar adalah {angka_rahasia}.")

# Menjalankan permainan
permainan_tebak_angka()
```
#### Output:
![Screenshot 2024-04-26 105728](https://github.com/ratihambara/Praktikum-Struktur-Data-Assignment/assets/161399790/df6bd4d8-813d-4627-976d-c28002973985)

Program ini menggunakan modul random untuk memilih angka secara acak antara 1 hingga 100.

### 6. Buat fungsi rekursif yang menerima input bilangan bulat `n`. Fungsi ini harus menggunakan konsep rekursi untuk menghitung faktorial setiap angka hingga `n` dan menghasilkan urutan bilangan seperti berikut ini: 
```
Input: n = 4
Output: 1, 1, 2, 6, 24
```

```
def faktorial(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * faktorial(n - 1)

def urutan_faktorial(n):
    hasil = []
    for i in range(n + 1):
        hasil.append(faktorial(i))
    return hasil

n = 4
print(f"Input: n = {n}")
print(f"Output: {', '.join(map(str, urutan_faktorial(n)))}")
```
#### Output:
![Screenshot 2024-04-26 105728](https://github.com/ratihambara/Praktikum-Struktur-Data-Assignment/assets/161399790/df6bd4d8-813d-4627-976d-c28002973985)

Fungsi faktorial(n) adalah fungsi rekursif yang menghitung faktorial dari n. Fungsi urutan_faktorial(n) menghasilkan urutan bilangan faktorial dari 0 hingga n dengan memanggil fungsi faktorial untuk setiap angka dalam rentang tersebut.

### 7. Buatlah program untuk memecahkan masalah "minimum coin change". Diberikan jumlah uang dan daftar nilai koin yang tersedia (misalnya, 1, 5, 10, 25), tentukan kombinasi minimum koin yang diperlukan untuk mencapai jumlah uang tersebut. Namun, program Anda harus bisa menangani koin-koin yang nilai dan jumlahnya ditentukan pengguna.

```
def minimum_coin_change(coins, jumlah):
    # Inisialisasi array untuk menyimpan jumlah minimum koin yang dibutuhkan untuk setiap jumlah
    dp = [float('inf')] * (jumlah + 1)
    dp[0] = 0  # Tidak ada koin yang dibutuhkan untuk jumlah 0

    # Mengisi array dp dengan jumlah minimum koin yang dibutuhkan
    for i in range(1, jumlah + 1):
        for coin in coins:
            if i - coin >= 0:
                dp[i] = min(dp[i], dp[i - coin] + 1)

    # Jika tidak mungkin mencapai jumlah dengan koin yang tersedia, kembalikan -1
    return dp[jumlah] if dp[jumlah] != float('inf') else -1

coins = [1, 5, 10, 25]
jumlah = 30
hasil = minimum_coin_change(coins, jumlah)
if hasil != -1:
    print(f"Jumlah minimum koin yang dibutuhkan untuk mencapai {jumlah} adalah {hasil}")
else:
    print(f"Tidak mungkin mencapai jumlah {jumlah} dengan koin yang tersedia")
```
#### Output:
![Screenshot 2024-04-26 105728](https://github.com/ratihambara/Praktikum-Struktur-Data-Assignment/assets/161399790/df6bd4d8-813d-4627-976d-c28002973985)

Program mengisi array dp dengan memeriksa setiap koin yang tersedia dan memperbarui jumlah minimum koin yang dibutuhkan. Jika tidak mungkin mencapai jumlah dengan koin yang tersedia, fungsi mengembalikan -1.

### 8. Buat sebuah program yang menerima string dari pengguna dan mengonversi string tersebut menjadi sebuah list berisi kata-kata terbalik. Misalnya:
```
Input: "Saya suka Python"
Output: ["ayaS", "akus", "nohtyP"]
```

```
def balik_kata(kalimat):
    # Memisahkan kalimat menjadi list kata-kata
    kata_kata = kalimat.split()
    
    # Membalik setiap kata dalam list
    kata_kata_terbalik = [kata[::-1] for kata in kata_kata]
    
    return kata_kata_terbalik

# Contoh penggunaan
kalimat = input("Masukkan kalimat: ")
hasil = balik_kata(kalimat)
print(hasil)
```
#### Output:
![Screenshot 2024-04-26 105728](https://github.com/ratihambara/Praktikum-Struktur-Data-Assignment/assets/161399790/df6bd4d8-813d-4627-976d-c28002973985)

Fungsi balik_kata(kalimat) memisahkan kalimat menjadi list kata-kata menggunakan split(). Setiap kata dalam list dibalik menggunakan slicing [::-1].

### 9. Buat class bernama `Buku` yang memiliki atribut `judul`, `penulis`, dan `tahun_terbit`. Buat method dalam class untuk menampilkan informasi buku, serta method untuk menghitung usia buku berdasarkan tahun saat ini. Buatlah 3 objek dari class `Buku` dan tampilkan informasi serta usia masing-masing buku.

```
from datetime import datetime

class Buku:
    def __init__(self, judul, penulis, tahun_terbit):
        self.judul = judul
        self.penulis = penulis
        self.tahun_terbit = tahun_terbit

    def tampilkan_informasi(self):
        print(f"Judul: {self.judul}")
        print(f"Penulis: {self.penulis}")
        print(f"Tahun Terbit: {self.tahun_terbit}")

    def hitung_usia(self):
        tahun_sekarang = datetime.now().year
        usia = tahun_sekarang - self.tahun_terbit
        return usia

# Membuat 3 objek dari class Buku
buku1 = Buku("Laskar Pelangi", "Andrea Hirata", 2005)
buku2 = Buku("Bumi Manusia", "Pramoedya Ananta Toer", 1980)
buku3 = Buku("Harry Potter and the Philosopher's Stone", "J.K. Rowling", 1997)

# Menampilkan informasi dan usia masing-masing buku
buku_list = [buku1, buku2, buku3]
for buku in buku_list:
    buku.tampilkan_informasi()
    print(f"Usia Buku: {buku.hitung_usia()} tahun\n")
```
#### Output:
![Screenshot 2024-04-26 105728](https://github.com/ratihambara/Praktikum-Struktur-Data-Assignment/assets/161399790/df6bd4d8-813d-4627-976d-c28002973985)

Method tampilkan_informasi digunakan untuk menampilkan informasi buku. Method hitung_usia digunakan untuk menghitung usia buku berdasarkan tahun saat ini.

### 10. Buatlah program yang mengimplementasikan algoritma pencarian biner, namun dengan modifikasi: algoritma harus bisa mencari nilai di list yang hanya berisi angka genap, dan jika nilai yang dicari adalah angka ganjil, program harus menampilkan pesan bahwa nilai tersebut tidak bisa ditemukan.

```
def binary_search_genap(arr, target):
    # Memeriksa apakah target adalah angka ganjil
    if target % 2 != 0:
        return "Nilai yang dicari adalah angka ganjil, tidak bisa ditemukan."

    low, high = 0, len(arr) - 1

    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return f"Nilai {target} ditemukan pada indeks {mid}."
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1

    return f"Nilai {target} tidak ditemukan dalam list."

list_genap = [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
target = 7
hasil = binary_search_genap(list_genap, target)
print(hasil)

target = 8
hasil = binary_search_genap(list_genap, target)
print(hasil)
```
#### Output:
![Screenshot 2024-04-26 105728](https://github.com/ratihambara/Praktikum-Struktur-Data-Assignment/assets/161399790/df6bd4d8-813d-4627-976d-c28002973985)

Fungsi binary_search_genap menerima list arr yang berisi angka genap dan target yang ingin dicari.

## Kesimpulan
Struct merupakan tipe data bentukan yang terdiri dari beberapa tipe data standar maupun tipe data bentukan lainnya yang telah didefinisikan sebelumnya. Keyword yang digunakan untuk membuat sebuah struktur yakni struct().

## Referensi
Sjukani, Moh. 2007. Struktur Data (Dasar-Dasar Python). Jakarta : Penerbit Mitra Wacana Media.

