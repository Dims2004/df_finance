# Personal Finance Dashboard (Excel)

Dashboard keuangan pribadi berbasis Excel untuk mencatat, menganalisis, dan memvisualisasikan pemasukan & pengeluaran bulanan. Dibuat menggunakan PivotTable, PivotChart, Slicer, dan formula `GETPIVOTDATA` untuk menampilkan ringkasan KPI secara interaktif.

##  Preview

> Tambahkan screenshot dashboard kamu di sini, misalnya:
> ![Dashboard Preview](aset/df%20finance.png)

## Fitur

- **Dashboard interaktif** dengan Slicer (filter berdasarkan Bulan & Akun)
- **KPI Section** — Total Income, Total Expense, Net Savings, Savings Rate, Budget Utilization, dan Current Balance yang dihitung otomatis dengan `GETPIVOTDATA`
- **Visualisasi**:
  - Tren pendapatan vs pengeluaran bulanan (line chart)
  - Pengeluaran berdasarkan kategori (donut chart)
  - Target tabungan berdasarkan jumlah (bar chart)
  - Anggaran vs aktual per kategori (bar chart)
  - Distribusi transaksi per akun & bank
- **Data transaksi lengkap** (441 transaksi, periode Januari–Desember 2026) mencakup kategori, sub-kategori, metode pembayaran, merchant, lokasi, dan status transaksi
- **Format nominal Rupiah (Rp)** dengan bank-bank Indonesia (BCA, BRI, BSI, Mandiri, BNI, CIMB Niaga)
- **Tombol Refresh Dashboard** (VBA macro) untuk me-refresh seluruh PivotTable sekaligus mereset filter slicer ke tampilan awal

## Struktur Sheet

| Sheet | Deskripsi |
|---|---|
| `Dataset` | Data mentah seluruh transaksi (sumber utama untuk PivotTable) |
| `Detail1` | Salinan/detail tambahan dari data transaksi |
| `Pivot` | Kumpulan PivotTable pendukung dashboard |
| `Dashboard` | Tampilan utama — ringkasan KPI, chart, dan slicer |

## Struktur Data (`Dataset`)

| Kolom | Keterangan |
|---|---|
| Transaction ID | ID unik transaksi |
| Date, Year, Month, Month No, Quarter | Informasi waktu transaksi |
| Account | Jenis akun (Savings, Credit Card, Wallet) |
| Bank | Bank terkait (BCA, BRI, BSI, Mandiri, BNI, CIMB Niaga) |
| Transaction Type | Income / Expense |
| Category, Sub Category | Kategori transaksi (Rent, Fuel, Grocery, Salary, dll) |
| Payment Method | Cash, Debit Card, Credit Card, Net Banking, UPI, Bank Transfer |
| Merchant | Nama merchant (Tokopedia, Shopee, Pertamina, Telkomsel, dll) |
| Amount (Rp), Budget (Rp) | Nominal transaksi & anggaran |
| Balance After Transaction (Rp) | Saldo akun setelah transaksi |
| Savings Goal | Tujuan tabungan (Vacation, Emergency Fund, Investment, Car) |
| Location | Lokasi transaksi (kota-kota di Indonesia) |
| Status, Recurring, Tax Deductible | Atribut tambahan transaksi |

## Cara Menggunakan

1. Download/clone repo ini.
2. Buka file `.xlsx` (atau `.xlsm` jika ingin memakai tombol refresh dengan macro) menggunakan **Microsoft Excel**.
3. Aktifkan **Macro** saat file dibuka (khusus versi `.xlsm`), agar tombol Refresh Dashboard berfungsi.
4. Gunakan **Slicer** di sheet Dashboard untuk memfilter data berdasarkan Bulan atau Akun.
5. Klik tombol **Refresh** untuk memperbarui seluruh PivotTable & mengembalikan tampilan ke kondisi awal (semua data).
6. Tambahkan transaksi baru langsung di sheet `Dataset`, lalu refresh dashboard untuk melihat pembaruan.

## Tools & Teknik yang Digunakan

- Microsoft Excel PivotTable & PivotChart
- Slicer untuk filter interaktif
- Formula `GETPIVOTDATA`, `INDEX`, `MATCH`, `IFERROR`
- VBA Macro sederhana untuk tombol refresh dashboard
- Excel Table (`tblTransactions`) sebagai sumber data dinamis

## Catatan

- Data pada dataset ini adalah **data simulasi/dummy** untuk keperluan latihan membangun dashboard keuangan pribadi, bukan data transaksi nyata.
- Cocok digunakan sebagai template awal untuk mencatat keuangan pribadi sendiri — tinggal ganti isi datanya sesuai kebutuhan.

## Lisensi

Bebas digunakan dan dimodifikasi untuk keperluan pribadi maupun pembelajaran.
