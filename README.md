# 🎵 ESP32 OLED Lyrics Display – SoundTante Edition

Proyek ini menampilkan lirik viral "Tante" secara otomatis pada layar OLED 128x64 menggunakan mikrokontroler ESP32. Cocok untuk kamu yang ingin belajar dasar-dasar mikrokontroler, komunikasi I2C, penggunaan library OLED, dan manipulasi teks secara visual.

---

## 📌 Tujuan Proyek

Menampilkan lirik satu per satu secara bergantian di layar OLED dengan tampilan yang rapi dan terpusat (centered). Lirik akan terus diulang dari awal setelah baris terakhir ditampilkan.

---

## 🧰 Komponen yang Dibutuhkan

| Komponen               | Jumlah | Keterangan                          |
|------------------------|--------|--------------------------------------|
| ESP32 Dev Board        | 1      | Bisa gunakan jenis DoIT / NodeMCU    |
| OLED Display 128x64    | 1      | Tipe I2C dengan chip SSD1306         |
| Kabel jumper male-male | 4      | Untuk koneksi antar pin              |
| Breadboard (opsional)  | 1      | Untuk merapikan sambungan kabel      |
| Laptop/PC + Arduino IDE| 1      | Untuk pemrograman dan upload kode    |

---

## 🔌 Wiring OLED ke ESP32

Pastikan kamu menghubungkan pin-pin OLED dengan benar ke ESP32:

| OLED Pin | ESP32 Pin |
|----------|-----------|
| GND      | GND       |
| VCC      | 3.3V      |
| SCL      | GPIO 22   |
| SDA      | GPIO 21   |

> ⚠️ Perhatikan tegangan VCC OLED. Pastikan sesuai dengan tipe modulmu. Kebanyakan modul OLED SSD1306 I2C mendukung 3.3V.

---

## 🖥️ Instalasi Library di Arduino IDE

1. Buka **Arduino IDE**.
2. Klik `Sketch > Include Library > Manage Libraries...`
3. Di kotak pencarian, cari dan **Install**:
   - `Adafruit GFX Library`
   - `Adafruit SSD1306`
4. Pastikan board ESP32 sudah diinstall (melalui Board Manager: cari `esp32` oleh Espressif Systems).

---

## 💾 Struktur File

```
ESP32-OLED-Lyrics/
├── SoundTante.ino       <- Kode utama proyek
└── README.md            <- Dokumentasi proyek ini
```

---

## 🔧 Upload Program ke ESP32

1. Hubungkan ESP32 ke komputer via kabel USB.
2. Buka `SoundTante.ino` di Arduino IDE.
3. Pilih board `Tools > Board > ESP32 Dev Module`.
4. Pilih port COM yang sesuai dari `Tools > Port`.
5. Klik tombol "Upload" (ikon panah kanan).
6. Setelah upload selesai, OLED akan menampilkan lirik.

---

## 📜 Penjelasan Program

- Menggunakan library Adafruit SSD1306 untuk mengontrol layar OLED.
- `lyrics[]` adalah array yang berisi setiap baris teks lirik.
- Fungsi `loop()` akan:
  1. Menghapus tampilan layar sebelumnya.
  2. Mengukur lebar dan tinggi teks yang akan ditampilkan.
  3. Menentukan posisi teks agar tampil di tengah layar.
  4. Menampilkan teks selama 980 milidetik.
  5. Pindah ke baris berikutnya dan mengulang.

---

## 🧪 Contoh Output (OLED)

```
------------------------
|                    |
|  Sudah terbiasa     |
|                    |
------------------------

Setelah 980 ms, baris akan berubah menjadi:

------------------------
|                    |
|      Terjadi        |
|                    |
------------------------
```

---

## 💡 Modifikasi yang Disarankan

- 🔊 Tambahkan audio player kecil (DFPlayer) agar sinkron dengan suara.
- 🎮 Tambahkan tombol untuk mengganti baris manual.
- 🧾 Tambahkan EEPROM/SDCard untuk menampilkan teks dari file.
- 🖋️ Ubah font atau efek animasi scrolling.

---

## 🧠 Troubleshooting

| Masalah                             | Solusi                                                 |
|------------------------------------|---------------------------------------------------------|
| Layar OLED tidak menyala           | Cek koneksi kabel dan pastikan pin VCC-GND benar       |
| Layar hanya putih/blank            | Pastikan alamat I2C 0x3C benar dan library terinstal   |
| Upload gagal ke ESP32              | Cek port COM, tekan tombol BOOT saat upload jika perlu |

---

## 👀 Referensi dan Inspirasi

- Library Adafruit: [SSD1306](https://github.com/adafruit/Adafruit_SSD1306), [GFX](https://github.com/adafruit/Adafruit-GFX-Library)

---

## 📝 Lisensi

Proyek ini terbuka untuk siapa saja yang ingin belajar dan mengembangkan kreativitas menggunakan ESP32. Bebas dimodifikasi dan disebarluaskan dengan menyertakan kredit pembuat asli.

---

## 🙋‍♂️ Kontributor

Dikembangkan oleh: **galihwibii**

Silakan fork, bintangi ⭐, dan bagikan ke teman-temanmu!
