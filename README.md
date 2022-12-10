Nama: Rafif Isdarufa Athallah

NIM: 312210299

Kelas: TI.22.A3

---

## Tugas Pratikum

### Diagram Class

![Diagram Class](https://github.com/zangetsuuuu/Pratikum8/blob/e482a2457566389e4ed79e7a20ce9ac9e53cb36d/gambar/Diagram%20Class.jpg)

### Flowchart

![Flowchart.jpg](https://github.com/zangetsuuuu/Pratikum8/blob/e482a2457566389e4ed79e7a20ce9ac9e53cb36d/gambar/Flowchart.jpg)

---

- Buat sebuah *dictionary* kosong untuk menampung data

```python
data_mahasiswa = {}
```

- Buat sebuah *Class* dan tambahkan atribut (nama, nim, tugas, uts, uas, total)
- *Class* adalah prototipe yang ditentukan pengguna untuk objek yang mendefinisikan sekumpulan atribut yang mendeskripsikan objek dari beberapa kelas
- Atribut adalah data anggota (variabel kelas dan variabel contoh) dan metode yang dapat diakses menggunakan notasi titik.
- Dalam *object-oriented-programming*/OOP, ketika mendefinisikan sebuah *method* untuk sebuah *class*, kita diharuskan untuk membuat `self` sebagai parameter pertama. `self` memungkinkan kita untuk mengakses ke atribut dan *method* pada setiap objek yang dibuat. Inilah yang membuat setiap objek memiliki atribut dan method nya masing - masing.

```python
class Mahasiswa:
    def __init__(self, nama="", nim=0, tugas=0, uts=0, uas=0, total=0.0):
        self.nama = nama
        self.nim = nim
        self.tugas = tugas
        self.uts = uts
        self.uas = uas
        self.total = total
```

- *Static method* adalah sebuah fungsi atau *method* pada sebuah *class* yang bersifat statis, yang dimana kita bisa memanggil fungsi tersebut secara langsung tanpa harus membuat *instance* dari *class* yang terkait. Untuk membuat *static method*, kita perlu mendefiniskan *decorator* `@staticmethod` diatas fungsi yang ingin dijadikan statis.
- Buat *method* `tampilkan()` yang berfungsi untuk menampilkan daftar nilai mahasiswa

```python
    @staticmethod
    def tampilkan():
        print("Daftar Nilai")
        if data_mahasiswa.items():
            print("=====================================================================================================")
            print("| No |           Nama           |       NIM       |   Tugas   |   UTS   |   UAS   |   Nilai Akhir   |")
            print("=====================================================================================================")
            i = 0
            for j in data_mahasiswa.items():
                i += 1
                print("| {no:2d} | {0:24s} | {1:15d} | {2:9d} | {3:7d} | {4:7d} | {5:15f} |".format(j[0][: 24], j[1][0], j[1][1], j[1][2], j[1][3], j[1][4], no=i))
            print("=====================================================================================================\n")

        else:
            print("=====================================================================================================")
            print("| No |           Nama           |       NIM       |   Tugas   |   UTS   |   UAS   |   Nilai Akhir   |")
            print("=====================================================================================================")
            print("|                                          TIDAK ADA DATA                                           |")
            print("=====================================================================================================\n") 
```

- Buat *method* `tambah()` yang berfungsi untuk menambah data mahasiswa dengan memasukkan nama, nim, nilai tugas, nilai UTS, nilai UAS.

```python
    def tambah(self):
        print("Tambah Data")
        self.nama = input("Nama        : ")
        self.nim = int(input("NIM         : "))
        self.tugas = int(input("Nilai Tugas : "))
        self.uts = int(input("Nilai UTS   : "))
        self.uas = int(input("Nilai UAS   : "))
        self.total = (self.tugas * 30 / 100) + (self.uts * 35 / 100) + (self.uas * 35 / 100)
        data_mahasiswa[self.nama] = self.nim, self.tugas, self.uts, self.uas, self.total
        print("Data berhasil ditambahkan!\n")
```

- Buat *method* `ubah()` yang berfungsi untuk mengubah data mahasiswa berdasarkan dengan nama data yang diinput

```python
    def ubah(self):
        print("Ubah Data")
        self.nama = input("Masukkan nama : ")
        if self.nama in data_mahasiswa.keys():
            self.nim = int(input("NIM           : "))
            self.tugas = int(input("Nilai Tugas   : "))
            self.uts = int(input("Nilai UTS     : "))
            self.uas = int(input("Nilai UAS     : "))
            self.total = (self.tugas * 30 / 100) + (self.uts * 35 / 100) + (self.uas * 35 / 100)
            data_mahasiswa[self.nama] = self.nim, self.tugas, self.uts, self.uas, self.total
            print("Data berhasil diubah!\n")

        else:
            print("Nama tidak ditemukan!\n")
```

- Buat *method* `hapus()` yang berfungsi untuk menghapus data mahasiswa berdasarkan data mahasiswa yang diinput

```python
    def hapus(self):
        print("Hapus Data")
        self.nama = input("Masukkan nama : ")
        if self.nama in data_mahasiswa.keys():
            del data_mahasiswa[self.nama]
            print("Data berhasil dihapus!\n")

        else:
            print("Data tidak ditemukan!\n")
```

- Gunakan `while` untuk melakukan perulangan
- Buat variabel untuk menginput data dari *user*
- ika user menginput '1', maka akan menjalankan *method* `tampilkan()`
- Jika user menginput '2', maka akan menjalankan *method* `tambah()`
- Jika user menginput '3', maka akan menjalankan *method* `ubah()`
- Jika user menginput '4', maka akan menjalankan *method* `hapus()`
- Jika user menginput '5', maka akan program akan berhenti dengan *statement* `break`

```python
while True:
    print("[ (1) Lihat Data,  (2) Tambah Data,  (3) Ubah Data,  (4) Hapus Data,  (5) Keluar ]")
    pilihan = input("Pilih menu: ")
    print()

    menu = Mahasiswa()
    if pilihan == "1":
        menu.tampilkan()

    elif pilihan == "2":
        menu.tambah()

    elif pilihan == "3":
        menu.ubah()

    elif pilihan == "4":
        menu.hapus()

    elif pilihan == "5":
        print("> Anda telah keluar dari program")
        break

    else:
        print("Kode tidak valid!\n")
```

---

#### Menu Lihat
![Lihat.jpg](https://github.com/zangetsuuuu/Pratikum8/blob/e482a2457566389e4ed79e7a20ce9ac9e53cb36d/gambar/Lihat.jpg)

#### Menu Tambah
![Tambah.jpg](https://github.com/zangetsuuuu/Pratikum8/blob/e482a2457566389e4ed79e7a20ce9ac9e53cb36d/gambar/Tambah.jpg)

#### Menu Ubah
![Ubah.jpg](https://github.com/zangetsuuuu/Pratikum8/blob/e482a2457566389e4ed79e7a20ce9ac9e53cb36d/gambar/Ubah.jpg)

#### Menu Hapus
![Hapus.jpg](https://github.com/zangetsuuuu/Pratikum8/blob/e482a2457566389e4ed79e7a20ce9ac9e53cb36d/gambar/Hapus.jpg)

#### Menu Keluar
![Keluar.jpg](https://github.com/zangetsuuuu/Pratikum8/blob/e482a2457566389e4ed79e7a20ce9ac9e53cb36d/gambar/Keluar.jpg)

---

### Sekian, terimakasih
