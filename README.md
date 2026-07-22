# wvi-oc3-threshold-analysis

Visualisasi analisis threshold indikator OC3 (WVI).

## Halaman

Halaman visualisasi ada di folder [`docs/`](docs/) dan bisa dipublikasikan lewat GitHub Pages:

1. Buka **Settings → Pages** di repo ini.
2. Pilih source **Deploy from a branch**, branch `main`, folder `/docs`.
3. Setelah aktif, halaman bisa diakses di `https://<username>.github.io/wvi-oc3-threshold-analysis/`.

Daftar halaman:
- `docs/index.html` — daftar semua halaman visualisasi
- `docs/opsi-threshold-per-indikator.html` — Opsi Threshold per Indikator (kelebihan, kekurangan & rekomendasi tiap indikator, P1&ndash;P4)
- `docs/ap-indicator-dashboard.html` — Dashboard Indikator per AP: kalkulasi nasional (tertimbang bobot HH target) & per Area Program dengan filter AP, indikator, status RC/Non-RC (sponsorship YAY09), partisipasi program (Direct/Indirect), wilayah (Rural/Urban), dan jenis kelamin

## Sumber data

Dashboard per AP diagregasi dari sheet `Indonesia_KOBO AIM_CL June 17_F` (Indonesia_Data_Dashboard_4.xlsx, 10.620 unit record) memakai kolom `IND*_Num`/`IND*_Denom` bawaan dataset. Data yang di-embed ke halaman sudah berupa agregat (tanpa data individu). Bobot nasional = HH Targeted per AP (total 64.417 HH), metode sama dengan Summary Dashboard workbook sumber; hasil divalidasi identik dengan sheet dashboard per indikator (mis. IND22 nasional tertimbang 13,15%).
