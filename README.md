# wvi-oc3-threshold-analysis

Threshold Analysis Dashboard — WVI PEARL Team. Menjelaskan dan memvisualisasikan mengapa threshold (benchmark mutu) penting sebelum penetapan target nasional, untuk 7 indikator OC3 AIM/AIM+ FY26.

## Halaman

Halaman ada di folder [`docs/`](docs/) dan dipublikasikan lewat GitHub Pages (**Settings → Pages → Deploy from a branch → `main` → `/docs`**), lalu diakses di `https://<username>.github.io/wvi-oc3-threshold-analysis/`.

Platform multi-halaman dengan navigasi global (Home · Dashboard · Evidence · Planning · Metodologi · Referensi):

- `docs/index.html` — **Home**: satu-satunya tempat konsep threshold (apa itu, mengapa penting, framework Baseline → Threshold → Annual Target → Long-term Outcome, klasifikasi status, dan Recommended Threshold Logic PEARL: P1 bila standar resmi ada → jika tidak P2 Best Performer → P3/P4 pendukung)
- `docs/threshold-dashboard.html` — **Dashboard** (analisis): filter tersinkron (indikator, AP, RC/Non-RC, gender, partisipasi, wilayah), National Summary, kartu indikator dengan **threshold selector P1–P4** (ubah basis threshold live), dan detail modal berisi tabel perbandingan 4 pendekatan + **Decision Panel** (rekomendasi, confidence, sumber bukti, alasan, tindakan)
- `docs/evidence.html` — **Evidence Intelligence**: garis waktu bukti (TP-CESP → AIM+ FY26 → endline FY30), riwayat & perbandingan per indikator, kualitas data (n, 95% CI Wilson, cakupan AP, kelengkapan) & kekuatan bukti terhitung, dan Baseline Review Panel dengan penanda otomatis. Modul yang butuh data masa depan ditandai "menunggu data" beserta skema pengisian
- `docs/planning.html` — **Outcome Planning**: rantai keputusan Approach → Baseline → Threshold → Gap → rekomendasi adaptif per indikator; modul Recommendation Tracker, Programming Reflection, Pathway of Change, Outcome Relationship, IPF Preparation sebagai scaffold "menunggu data" + skema
- `docs/methodology.html` — **Metodologi**: 4 pendekatan (P1–P4) + logika pemilihan + cara perhitungan baseline
- `docs/references.html` — **Referensi**: kerangka M&E internasional + sumber data
- `docs/opsi-threshold-per-indikator.html` — lampiran teknis P1–P4 per indikator
- `docs/ap-indicator-dashboard.html` — redirect ke `threshold-dashboard.html` (halaman lama)

### Evidence Intelligence — status data

Evidence & Planning menerapkan pola **scaffold + template**: menampilkan data nyata yang tersedia (baseline AIM+ FY26; riwayat TP-CESP untuk Indicator 6, 7, 22; CI/cakupan/kekuatan bukti terhitung) dan menandai sisanya "menunggu data" dengan skema pengisian. Tidak ada data studi yang dikarang. Sumber yang perlu dilengkapi PEARL: TP-CESP lengkap, evaluasi sebelumnya, studi riset, household survey, sector assessment, status implementasi rekomendasi, Theory of Change (Goal→Outcome→Output→Activity), budget/staffing, dan relasi antar-outcome. Skema JSON ada di dalam `evidence.html`/`planning.html` (bagian "Menunggu Data").

## Sumber data

- **Metadata threshold & rasional**: `Analisis_4_Pendekatan_Threshold_OC3_FINAL.xlsx` (sheet Data_Dasar, P1–P4, Summary_Rekomendasi, Triangulasi, Definisi_Threshold). Threshold usulan: OIOS 22 → 10%; OIOS 6 → 64,60%; OIOS 7 → 45,23%; OIOS 10 → 26,25%; OIOS 157 → ±61,7% (sementara); C2A.027994 → ±31,0% (sementara); OIOS 27 → ditunda. Semua berlabel "usulan untuk didiskusikan".
- **Data filterabel**: unit record sheet `Indonesia_KOBO AIM_CL June 17_F` (10.620 baris, 9 AP), diagregasi per AP × wilayah × status RC (YAY09) × partisipasi (OIOS_xx_direct) × jenis kelamin memakai kolom `IND*_Num`/`IND*_Denom`. Yang di-embed ke halaman hanya agregat.
- **Bobot nasional**: HH Targeted per AP (total 64.417 HH); baseline tertimbang tervalidasi identik dengan workbook sumber (mis. OIOS 22 = 13,15%).
