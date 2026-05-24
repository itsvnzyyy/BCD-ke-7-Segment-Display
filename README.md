# 🚀 Rangkaian BCD ke 7-Segment Display Menggunakan IC CD4511

Laporan Praktikum Sistem Digital - **Modul VIII** Nama: **Alvin Syahrinaldi** | NIM: **H1H025040** Shift: **B -> C**

---

## 📌 Deskripsi Proyek
Proyek ini merupakan simulasi rangkaian **BCD (Binary Coded Decimal) ke 7-Segment Display** menggunakan **IC CD4511** sebagai decoder dan **DIP Switch 4-Bit** sebagai input generator. Simulasi ini dibuat dan diuji secara virtual melalui platform **Tinkercad Circuits**.

---

## 🛠️ Tata Letak & Skematik Rangkaian

Berikut adalah visualisasi hasil *wiring* komponen yang dirancang pada ruang kerja Tinkercad:

![Skematik Rangkaian](https://images.squarespace-cdn.com/content/v1/5f3ffbe13ed7dc6ee58e9947/1715878479374-S7C26F9M0H7W6DURD7H3/image-asset.png) 
*(Catatan: Anda bisa mengganti URL gambar di atas dengan hasil screenshot rangkaian Anda sendiri jika sudah di-upload ke GitHub)*

### Komponen Utama yang Digunakan:
* **1x** IC CD4511 (BCD to 7-Segment Decoder)
* **1x** 7-Segment Display (Tipe *Common Cathode*)
* **1x** DIP Switch 4-Bit
* **4x** Resistor 1 kΩ (Sebagai *Pull-down*)
* **1x** Power Supply 5V

---

## 📊 Tabel Kebenaran (Hasil Percobaan)

Konfigurasi sakelar diatur dengan menetapkan **SW1 sebagai MSB (Bit D)** dan **SW4 sebagai LSB (Bit A)** agar urutan input biner selaras secara visual dari kiri ke kanan.

| No | D (SW1) | B (SW2) | C (SW3) | A (SW4) | Tampilan | Segmen Aktif (a-g) |
|:--:|:-------:|:-------:|:-------:|:-------:|:--------:|:------------------:|
| 1  |    0    |    0    |    0    |    0    |    0     | a, b, c, d, e, f   |
| 2  |    0    |    0    |    0    |    1    |    1     | b, c               |
| 3  |    0    |    0    |    1    |    0    |    2     | a, b, d, e, g      |
| 4  |    0    |    0    |    1    |    1    |    3     | a, b, c, d, g      |
| 5  |    0    |    1    |    0    |    0    |    4     | b, c, f, g         |
| 6  |    0    |    1    |    0    |    1    |    5     | a, c, d, f, g      |
| 7  |    0    |    1    |    1    |    0    |    6     | c, d, e, f, g      |
| 8  |    0    |    1    |    1    |    1    |    7     | a, b, c            |
| 9  |    1    |    0    |    0    |    0    |    8     | a, b, c, d, e, f, g|
| 10 |    1    |    0    |    0    |    1    |    9     | a, b, c, d, f, g   |

> ⚠️ **Info Penting:** Jika input biner dimasukkan melebihi `1001` (desimal 10–15), layar display akan otomatis mati (*blanking*) karena input tersebut tidak valid dalam pengkodean BCD.

---

## 📝 Kesimpulan Analisis

* **Prinsip Kerja Dekoder:** IC CD4511 berhasil mengubah kode biner 4-bit dari DIP Switch menjadi sinyal paralel yang menyalakan kombinasi segmen LED tertentu (a-g) untuk memunculkan angka desimal 0-9.
* **Kesesuaian Komponen:** Karena IC CD4511 bekerja dengan logika aktif-tinggi (*Active-HIGH*), rangkaian ini wajib dipasangkan dengan *7-Segment Display* tipe **Common Cathode** yang pin bersamanya dihubungkan ke *Ground* (GND).
* **Fungsi Resistor Pull-down:** Pemasangan 4 buah resistor 1 kΩ berfungsi sebagai penstabil tegangan agar input IC berada pada logika 0 murni saat sakelar mati (*OFF*), sehingga mencegah terjadinya error akibat sinyal mengambang (*floating logic*).

---

## 🔗 Tautan Eksternal

* **Tinkercad Project:** [Buka Simulasi Rangkaian](https://www.tinkercad.com/things/aHE5EhYyR86-bcd-ke-7-segment)
