# wvi-oc3-threshold-analysis

Threshold Analysis Dashboard — WVI PEARL Team. Menjelaskan dan memvisualisasikan mengapa threshold (benchmark mutu) penting sebelum penetapan target nasional, untuk 7 indikator OC3 AIM/AIM+ FY26.

## Halaman

Halaman ada di folder [`docs/`](docs/) dan dipublikasikan lewat GitHub Pages (**Settings → Pages → Deploy from a branch → `main` → `/docs`**), lalu diakses di `https://<username>.github.io/wvi-oc3-threshold-analysis/`.

- `docs/index.html` — beranda
- `docs/threshold-dashboard.html` — **Threshold Analysis Dashboard** (halaman utama): konsep threshold, mengapa penting, framework Baseline → Threshold → Annual Target → Long-term Outcome, klasifikasi status (Critical / Need Improvement / Acceptable / Excellent), filter (indikator, AP, RC/Non-RC, gender, partisipasi, wilayah) yang menggerakkan National Summary + kartu analisis per indikator, detail interaktif per indikator (definisi, perhitungan, rasional 4 pendekatan, distribusi, perbandingan AP/gender/RC, rekomendasi, bukti), landasan literatur, dan key message
- `docs/opsi-threshold-per-indikator.html` — lampiran teknis P1–P4 per indikator
- `docs/ap-indicator-dashboard.html` — redirect ke `threshold-dashboard.html` (halaman lama)

## Sumber data

- **Metadata threshold & rasional**: `Analisis_4_Pendekatan_Threshold_OC3_FINAL.xlsx` (sheet Data_Dasar, P1–P4, Summary_Rekomendasi, Triangulasi, Definisi_Threshold). Threshold usulan: OIOS 22 → 10%; OIOS 6 → 64,60%; OIOS 7 → 45,23%; OIOS 10 → 26,25%; OIOS 157 → ±61,7% (sementara); C2A.027994 → ±31,0% (sementara); OIOS 27 → ditunda. Semua berlabel "usulan untuk didiskusikan".
- **Data filterabel**: unit record sheet `Indonesia_KOBO AIM_CL June 17_F` (10.620 baris, 9 AP), diagregasi per AP × wilayah × status RC (YAY09) × partisipasi (OIOS_xx_direct) × jenis kelamin memakai kolom `IND*_Num`/`IND*_Denom`. Yang di-embed ke halaman hanya agregat.
- **Bobot nasional**: HH Targeted per AP (total 64.417 HH); baseline tertimbang tervalidasi identik dengan workbook sumber (mis. OIOS 22 = 13,15%).
