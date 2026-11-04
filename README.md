# PERTEMUAN 13 - DEBUGGING DAN TESTING

**Nama:** Sela Widiyanti
**NIM:** 2225250176  
**Kelas:** 3F 

## 1. Deskripsi Praktik

Praktik pertemuan 13 membahas debugging, tracing, testing, dan test case menggunakan Python di VS Code. Kegiatan ini bertujuan untuk menemukan kesalahan pada program, mengetahui penyebabnya, memperbaiki kode, serta melakukan pengujian ulang untuk memastikan program berjalan dengan benar.

## 2. Struktur Folder

```text
pertemuan-13-debugging-NIM/
│
├── README.md
├── .gitignore
│
├── kasus/
│   ├── kasus_01_batas_kelulusan.py
│   ├── kasus_02_rata_rata.py
│   └── kasus_03_file_nilai.py
│
├── latihan/
│   ├── 01_trace_loop.py
│   ├── 02_trace_fungsi.py
│   ├── 03_test_case.py
│   └── 04_debug_breakpoint.py
│
└── praktik/
    └── praktik_4_debugging.py
```

## 3. Kasus yang Diuji

Program yang diuji merupakan program pengolahan nilai mahasiswa. Program memiliki tiga fungsi utama, yaitu menghitung rata-rata nilai, menentukan status kelulusan, dan mencari nilai tertinggi.

Pada program awal ditemukan tiga kesalahan yang menyebabkan hasil program tidak sesuai dengan yang diharapkan.

## 4. Test Case

| ID | Input | Expected | Actual Awal | Status Awal |
|---|---|---|---|---|
| T1 | [80,60,90,70] | 75.0 | 60.0 | FAIL |
| T2 | [100,80] | 90.0 | 36.0 | FAIL |
| T3 | 60 | Lulus | Tidak lulus | FAIL |
| T4 | 59 | Tidak lulus | Tidak lulus | PASS |
| T5 | [80,60,90,70] | 90 | 0 | FAIL |

## 5. Bug Report

### Bug 01 - Perhitungan Rata-rata

- **Gejala:** Hasil rata-rata tidak sesuai dengan jumlah data.
- **Lokasi:** Fungsi `hitung_rata_rata()`.
- **Akar penyebab:** Pembagi menggunakan angka tetap 5.
- **Perbaikan:** Mengganti pembagi dengan `len(nilai)` serta menambahkan pemeriksaan list kosong.

### Bug 02 - Status Kelulusan

- **Gejala:** Nilai 60 dianggap tidak lulus.
- **Lokasi:** Fungsi `status()`.
- **Akar penyebab:** Operator pembanding menggunakan `>` sehingga nilai 60 tidak termasuk lulus.
- **Perbaikan:** Mengubah operator menjadi `>=`.

### Bug 03 - Nilai Tertinggi

- **Gejala:** Program tidak menghasilkan nilai tertinggi dengan benar.
- **Lokasi:** Fungsi `nilai_tertinggi()`.
- **Akar penyebab:** Operator pembanding menggunakan `<` dan nilai awal ditetapkan 0.
- **Perbaikan:** Menggunakan nilai pertama sebagai nilai awal dan mengganti operator menjadi `>`.

## 6. Hasil Retest

Setelah dilakukan perbaikan, seluruh test case dijalankan kembali.

| ID | Expected | Actual Setelah Perbaikan | Status |
|---|---|---|---|
| T1 | 75.0 | 75.0 | PASS |
| T2 | 90.0 | 90.0 | PASS |
| T3 | Lulus | Lulus | PASS |
| T4 | Tidak lulus | Tidak lulus | PASS |
| T5 | 90 | 90 | PASS |

Hasil pengujian menunjukkan bahwa seluruh test case berhasil dan program sudah menghasilkan output sesuai dengan yang diharapkan.

## 7. Cara Menjalankan Program

Pastikan Python sudah terinstal, kemudian buka terminal VS Code dan jalankan perintah:

```bash
python praktik/praktik_4_debugging.py
```

## 8. Teknik Debugging

Teknik yang digunakan dalam praktik ini meliputi:

1. Tracing untuk mengamati perubahan nilai variabel.
2. Breakpoint untuk menghentikan program pada baris tertentu.
3. Step Over untuk menjalankan kode baris demi baris.
4. Step Into untuk menelusuri fungsi.
5. Testing untuk membandingkan hasil yang diharapkan dengan hasil aktual.

## 9. Refleksi

Dari praktik ini, saya memahami bahwa program yang berhasil dijalankan belum tentu menghasilkan jawaban yang benar. Oleh karena itu, diperlukan debugging dan testing untuk menemukan kesalahan serta memperbaiki penyebabnya. Saya juga belajar bahwa pengujian ulang penting dilakukan agar perbaikan tidak menimbulkan kesalahan baru.

## 10. Kesimpulan

Melalui kegiatan pertemuan 13, saya dapat memahami cara menemukan dan memperbaiki bug pada program Python menggunakan VS Code. Selain itu, saya belajar membuat test case, menggunakan debugger, serta mendokumentasikan hasil perbaikan melalui README.md dan GitHub.

"docs: menambahkan hasil retest dan refleksi"