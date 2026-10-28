# Pertemuan 13 - Debugging dan Testing

Nama: Angelita Juliana Siahaan
NIM: 2225250112
Kelas: 3B

## Kasus
Program pengolah data nilai mahasiswa yang mencakup perhitungan rata-rata, penentuan status kelulusan, dan pencarian nilai tertinggi.

## Test Case
| ID | Target | Input | Expected | Actual Awal | Status |
|---|---|---|---|---|---|
| T1 | rata-rata | [80, 60, 90, 70] | 75.0 | 75.0 | PASS |
| T2 | rata-rata | [100, 80] | 90.0 | 36.0 | FAIL |
| T3 | status | 60 | Lulus | Tidak lulus | FAIL |
| T4 | status | 59 | Tidak lulus | Tidak lulus | PASS |
| T5 | tertinggi | [80, 60, 90, 70] | 90 | 0 | FAIL |

## Bug Report
- **B01 (Rata-rata)**: Pembagi di-hardcode angka 5. Diperbaiki dengan membagi menggunakan `len(nilai)`.
- **B02 (Status)**: Menggunakan operator `> 60` sehingga nilai 60 gagal lulus. Diperbaiki menjadi `>= 60`.
- **B03 (Nilai Tertinggi)**: Logika perbandingan salah (`x < tertinggi`). Diperbaiki menjadi `x > tertinggi`.

## Retest
Seluruh test case berhasil dijalankan kembali dan menghasilkan status **PASS** tanpa adanya regresi.

## Cara Menjalankan
python3 praktik/praktik_4_debugging.py

## Refleksi
Teknik debugging yang paling membantu adalah penggunaan test case dan breakpoint karena kita bisa mencari akar masalah secara sistematis, bukan cuma nebak-nebak.