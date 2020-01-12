# Tugas Praktikum 5

## Buat program sederhana yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan :
* Program dibuat dengan menggunakan **Dictionary**
* Tampilkan menu pilihan : (Tambah Data, Ubah Data, Hapus Data, Tampilkan Data, Cari Data)
* Nilai akhir diambil dari perhitungan 3 komponen nilai tugas (tugas: 30%, uts: 35%, uas: 35%)
* Buat flowchart dan penjelasan programnya pada Readme.md
* Commit dan push repository

## Penjelasan
* Dictionary yang telah didefinisikan ```daftar = {}```
* Perulangan yang digunakan terus menerus selama memenuhi syarat ```while True:```
* Menampilkan menu pilihan
```
print("\n=================================================")
    perintah = input("(L) Lihat, (T) Tambah, (U) Ubah, \n"
                     "(H) Hapus, (C) Cari, (K) Keluar: ")
    print("=================================================")
```
* Output

![tampilan menu](https://user-images.githubusercontent.com/56512562/72223206-f3d2ba00-359e-11ea-9077-ab38c3bd69a2.png)

### 1) Tambah Data
```
# Tambah
    elif perintah.lower() == 't':
        print("Masukan data mahasiswa")
        print("...")
        nama = input("Masukan nama: ")
        nim = input("Masukan NIM: ")
        n_tugas = int(input("Masukan nilai tugas: "))
        n_UTS = int(input("Masukan nilai UTS: "))
        n_UAS = int(input("Masukan nilai UAS: "))
        a = n_tugas * 30 / 100
        b = n_UTS * 35 / 100
        c = n_UAS * 35 / 100
        n_akhir = a + b + c
        daftar[nama] = [nama, nim, n_tugas, n_UTS, n_UAS, n_akhir]
```
* Kondisi yang memungkinkan pengguna untuk mengisi data.
* Dan nilai akhir didapatkan oleh operasi variabel yg dihasilkan dari nilai tugas, uts, dan uas.
* Output

![tambah data](https://user-images.githubusercontent.com/56512562/72223205-f3d2ba00-359e-11ea-8229-f3b409372279.png)

### 2) Menampilkan Data
```
# Lihat
    elif perintah.lower() == 'l':
        print("Daftar Nilai:")
        print("===================================================================")
        print("| No |      Nama      |    NIM    | Tugas |  UTS  |  UAS  | Akhir |")
        print("===================================================================")
        no = 1
        for tabel in daftar.values():
            print("| {0:2} | {1:14} | {2:9} | {3:5} | {4:5} | {5:5} | {6:5} |".format
                  (no, tabel[0],
                   tabel[1], tabel[2],
                   tabel[3], tabel[4], tabel[5]))
            no += 1
```
* Kondisi yang menampilkan data yang berada didalamnya
* Output

![menampilkan data](https://user-images.githubusercontent.com/56512562/72223208-f46b5080-359e-11ea-81d5-39f1a7748c4b.png)

### 3) Mengubah Data
```
elif perintah.lower() == 'u':
        nama = input("Masukan nama untuk mengubah data: ")
        if nama in daftar.keys():
            print("Masukan data yang ingin di ubah :")
            data = input("(Semua), (Nama), (NIM), "
                         "(Tugas), (UTS), (UAS) : ")
```
* Kondisi yang dapat mengubah data yang ada, dan apa saja yg dapat diubah yaitu
```
if data.lower() == "semua":
                print("==========================")
                print("Ubah data {}.".format(nama))
                print("==========================")
                daftar[nama][1] = input("Edit NIM:")
                daftar[nama][2] = int(input("Edit Nilai Tugas: "))
                daftar[nama][3] = int(input("Edit Nilai UTS: "))
                daftar[nama][4] = int(input("Edit Nilai UAS: "))
                # print(daftar)
            elif data.lower() == "nim":
                daftar[nama][1] = input("NIM:")
            elif data.lower() == "tugas":
                daftar[nama][2] = int(input("Nilai Tugas: "))
            elif data.lower() == "uts":
                daftar[nama][3] = int(input("Nilai UTS: "))
            elif data.lower() == "uas":
                daftar[nama][4] = int(input("Nilai UAS: "))
```
* Output

![mengubah data](https://user-images.githubusercontent.com/56512562/72223204-f33a2380-359e-11ea-8579-30c8eba00e40.png)

### 4) Mencari Data
```
    # Cari
    elif perintah.lower() == 'c':
        print("Mencari daftar nilai: ")
        print("=================================================")
        nama = input("Masukan nama untuk mencari daftar nilai : ")
        if nama in daftar.keys():
            print("Nama {0}, dengan NIM : {1}\n"
                  "Nilai Tugas: {2}, UTS: {3}, dan UAS: {4}\n"
                  "dan nilai akhir {5}".format(nama, daftar[nama][1],
                                               daftar[nama][2], daftar[nama][3],
                                               daftar[nama][4], daftar[nama][5]))
        else:
            print("'{}' tidak ditemukan.".format(nama))
```
* Kondisi pengguna dapat mencari data yang diinginkan berdasarkan pencarian nama
* Output

![mencari data](https://user-images.githubusercontent.com/56512562/72223209-f46b5080-359e-11ea-87f3-a4ddba3bdce4.png)

### 5) Menghapus Data
```
# Hapus
    elif perintah.lower() == 'h':
        nama = input("Masukan nama untuk menghapus data : ")
        if nama in daftar.keys():
            del daftar[nama]
            print("Data '{}' dihapus.".format(nama))
        else:
            print("'{}' tidak ditemukan.".format(nama))
```
* Pengguna dapat menghapus data yang ada dalam list
* Output

![menghapus data](https://user-images.githubusercontent.com/56512562/72223210-f503e700-359e-11ea-8753-f50818d8e161.png)

### Keluar Program
* Statment yang memberhentikan perulangan
```
if perintah.lower() == 'k':
        break
```
* Output

![keluar](https://user-images.githubusercontent.com/56512562/72223207-f46b5080-359e-11ea-9b77-7ea08ec730ce.png)

# Terima Kasih
