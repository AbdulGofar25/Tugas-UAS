**Nama          : Abdul Gofar** <br>
**Nim           : 312210504** <br>
**Kelas         : TI.22.B2** <br>
**Mata Kuliah   : Bahasa Pemrograman** <br>
**Program Studi : Teknik Informatika** <br>
**Dosen Pengampu: Agung Nugroho, M.Kom** <br>

# Tugas UAS Bahasa Pemrograman

![Gambar 1](gambar/ss1.png) <br>

## Link video program di Yt
https://youtu.be/uX3F-bNj2vE

## ••Buatalah Package Modul dengan struktur seperti berikut :
√daftar_nilai.py berisi modul untuk: <br>
tambah_data, ubah_data, hapus_data,
dan cari_data <br>
✓ view_nilai.py berisi modul untuk: <br>
cetak_daftar_nilai, cetak_hasil_pencarian <br>
✓ input_nilai.py berisi modul untuk: <br>
input_data yang meminta pengguna
memasukkan data. <br>
✓ main.py berisi program utama (menu
pilihan yang memanggil semua menu
yang ada) 


## •Dibawah ini adalah script untuk daftar_nilai.py
 →Berisi modul untuk : tambah_data, ubah_data, hapus_data, dan cari_data <br>

from View.input_nilai import  <br>

data = {} <br>

def tambah_data(): <br>
    print("====Tambah Data====") <br>
    global data <br>
    nama = input_nama() <br>
    nim = input_nim() <br>
    nilaiTugas = input_nilaiTugas() <br>
    nilaiUts = input_nilaiUts() <br>
    nilaiUas = input_nilaiUas() <br>
    nilaiAkhir = (0.30 * nilaiTugas) + (0.35 * nilaiUts) + (0.35 * nilaiUas) <br>
    data[nama] = nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir <br>
    print("\nData Berhasil Ditambahkan!") <br>
    return data <br>

def ubah_data(): <br>
    print("====Ubah Data====") <br>
    nama = input("Masukkan Nama: ") <br>
    if nama in data.keys(): <br>
        nim           = input_nim() <br>
        nilaiTugas    = input_nilaiTugas() <br>
        nilaiUts      = input_nilaiUts() <br>
        nilaiUas      = input_nilaiUas() <br>
        nilaiAkhir    = (0.30 * nilaiTugas) + (0.35 * nilaiUts) + (0.35 * nilaiUas) <br>
        data[nama]    = nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir <br>
        print("\nData Berhasil Di Update!") <br>
    else: <br>
        print("Data tidak ditemukan!") <br>

def hapus_data(): <br>
    print("====Hapus Data====") <br>
    nama = input("Masukkan Nama:  ") <br>
    if nama in data.keys(): <br>
        del data[nama] <br>
        print("Data",nama,"Telah dihapus!") <br>
    else: <br>
        print("Data Mahasiswa Tidak Ada".format(nama)) <br>

## Gambar inputan
![Gambar 2](gambar/ss2.png) <br>
![Gambar 3](gambar/ss3.png) <br>

## •Dibawah ini adalah Script untuk view_nilai.py
 →Berisi modul untuk : cetak_daftar_nilai, cetak_hasil_pencarian <br>

 from model.daftar_nilai import  <br>

def cetak_daftar_nilai():<br>
    print("====Lihat Data====")<br>
    if data.items():<br>
        print("\n Daftar Nilai Mahasiswa ")<br>
        print("==================================================================")<br>
        print("| No |     Nama     |    NIM    | Tugas |  UTS  |  UAS  |  Akhir |")<br>
        print("==================================================================")<br>
        i = 0<br>
        for x in data.items():<br>
            i += 1<br>
            print("| {6:2} | {0:12s} | {1:9s} | {2:5} | {3:5} | {4:5} | {5:6} |".format(x[0], x[1][0], x[1][1], x[1][2],<br>
                                                                                        x[1][3], x[1][4], i))<br>
        print("==================================================================")<br>
    else:<br>
        print("\n Daftar Nilai Mahasiswa ")<br>
        print("==================================================================")<br>
        print("| No |     Nama     |    NIM    | Tugas |  UTS  |  UAS  |  Akhir |")<br>
        print("==================================================================")<br>
        print("|                          TIDAK ADA DATA                        |")<br>
        print("==================================================================")<br>

def cetak_hasil_pencarian():<br>
    print("====Cari Data====")<br>
    nama = input("Masukkan Nama        : ")<br>
    if nama in data.keys():<br>
        print("\n Daftar Nilai Mahasiswa ")<br>
        print("==============================================================")<br>
        print("|     Nama     |    NIM    | Tugas |  UTS  |  UAS  |  Akhir  |")<br>
        print("==============================================================")<br>
        print("| {0:12s} | {1:9s} | {2:5} | {3:5} | {4:5} | {5:6}  |"<br>
              .format(nama, data[nama][0], data[nama][1],data[nama][2], data[nama][3],data[nama][4]))<br>
        print("==============================================================")<br>
    else:<br>
        print("Data {0} Tidak Ada ".format(nama))<br>

## Gambar inputan
![Gambar 4](gambar/ss4.png) <br>
![Gambar 5](gambar/ss5.png) <br>

## •Dibawah ini adalah Script untuk input_nilai.py
 →Berisi modul untuk : input_data yang meminta pengguna untuk memasukan data<br>

def input_nama():<br>
    global nama<br>
    nama = input("Masukkan Nama anda        : ")<br>
    return nama<br>

def input_nim():<br>
    global nim<br>
    nim = input("Masukkan NIM  anda         : ")<br>
    return nim<br>

def input_nilaiTugas():<br>
    global nilaiTugas<br>
    nilaiTugas = int(input("Masukkan Nilai Tugas : "))<br>
    return nilaiTugas<br>

def input_nilaiUts():<br>
    global nilaiUts<br>
    nilaiUts = int(input("Masukkan Nilai UTS   : "))<br>
    return nilaiUts<br>

def input_nilaiUas():<br>
    global nilaiUas<br>
    nilaiUas = int(input("Masukkan Nilai UAS   : "))<br>
    return nilaiUas<br>

## Gambar inputan
![Gambar 6](gambar/ss6.png) <br>

## •Dibawah ini adalah script untuk main.py
 →Berisi program utama (menu pilihan yang memanggil semua menu yang ada)<br>

from View.view_nilai import *<br>

while True:<br>
    c = input("\n(T)ambah, (U)bah, (H)apus, (C)ari, (L)ihat, (K)eluar: ")<br>

    if (c.lower() == 't'): 
        tambah_data()

    elif (c.lower() == 'u'):
        ubah_data()

    elif (c.lower() == 'h'):
        hapus_data()

    elif (c.lower() == 'c'):
        cetak_hasil_pencarian()

    elif (c.lower() == 'l'):
        cetak_daftar_nilai()

    elif (c.lower() == 'k'):
        break

    else: 
        print("=== Pilih Sesuai Menu Yang Tersedia ===")

## Gambar inputan
![Gambar 7](gambar/ss7.png) <br>

## Berikut adalah hasil output programnya
• Dibawah ini adalah hasil program ketika input data dan menambahkan data
![Gambar 8](gambar/ss8.png) <br>

• Dibawah ini adalah hasil program menampilkan data dan mencari data
![Gambar 9](gambar/ss9.png) <br>


• Dibawah ini adalah hasil program ubah data
![Gambar 10](gambar/ss10.png) <br>

• Dibawah ini adalah hasil program hapus data
![Gambar 11](gambar/ss11.png) <br>

## Selesai
### Sekian dan Terimakasih semoga membantu 🙏😊
