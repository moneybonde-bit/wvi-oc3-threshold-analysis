# wvi-oc3-threshold-analysis

Threshold Analysis Platform (World Vision Indonesia). Menjelaskan dan memvisualisasikan mengapa threshold (benchmark mutu) penting sebelum penetapan target nasional, untuk 7 indikator OC3 AIM/AIM+ FY26.

## Halaman

Halaman ada di folder [`docs/`](docs/) dan dipublikasikan lewat GitHub Pages (**Settings → Pages → Deploy from a branch → `main` → `/docs`**), lalu diakses di `https://<username>.github.io/wvi-oc3-threshold-analysis/`.

Platform multi-halaman dengan navigasi global (Home · Dashboard · Opsi Threshold · Evidence · Planning · Metodologi · Referensi):

- `docs/index.html` — **Home**: satu-satunya tempat konsep threshold (apa itu, mengapa penting, framework Baseline → Threshold → Annual Target → Long-term Outcome, klasifikasi status, dan Logika Pemilihan Threshold: rekomendasi utama = P2 Best Performer (level yang sudah terbukti dicapai AP nyata; positive deviance / internal benchmarking), dengan P1 sebagai acuan resmi bila ada dan P3/P4 sebagai pembanding)
- `docs/threshold-dashboard.html` — **Dashboard** (analisis): filter tersinkron, National Summary, kartu indikator dengan **threshold selector P1–P4** (ubah basis threshold live), dan detail modal berisi tabel perbandingan 4 pendekatan + **Decision Panel**. Pilihan P1–P4 per indikator **tersinkron dengan halaman Opsi Threshold** via localStorage
- `docs/evidence.html` — **Evidence Intelligence**: garis waktu bukti (TP-CESP → AIM+ FY26 → endline FY30), riwayat & perbandingan per indikator, kualitas data (n, 95% CI Wilson, cakupan AP, kelengkapan) & kekuatan bukti terhitung, dan Baseline Review Panel dengan penanda otomatis. Modul yang butuh data masa depan ditandai "menunggu data" beserta skema pengisian
- `docs/planning.html` — **Outcome Planning**: rantai keputusan Approach → Baseline → Threshold → Gap → rekomendasi adaptif per indikator; modul Recommendation Tracker, Programming Reflection, Pathway of Change, Outcome Relationship, IPF Preparation sebagai scaffold "menunggu data" + skema
- `docs/methodology.html` — **Metodologi**: 4 pendekatan (P1–P4) + logika pemilihan + cara perhitungan baseline
- `docs/references.html` — **Referensi**: kerangka M&E internasional + sumber data
- `docs/opsi-threshold-per-indikator.html` — **Opsi Threshold**: satu kartu per indikator (semua 7) dengan keempat kandidat P1–P4 + selector yang **tersinkron dengan dashboard**, ★ menandai rekomendasi (P2), dan bagian **"Mengapa P2 direkomendasikan?"** (alasan & landasan teori: achievability, konteks, positive deviance, benchmarking). P2 = nilai best-performer AP tunggal yang nyata (bisa outlier)
- `docs/ap-indicator-dashboard.html` — redirect ke `threshold-dashboard.html` (halaman lama)

### Evidence Intelligence — status data

Evidence & Planning menerapkan pola **scaffold + template**: menampilkan data nyata yang tersedia (baseline AIM+ FY26; riwayat TP-CESP untuk Indicator 6, 7, 22; CI/cakupan/kekuatan bukti terhitung) dan menandai sisanya "menunggu data" dengan skema pengisian. Tidak ada data studi yang dikarang. Sumber yang perlu dilengkapi: TP-CESP lengkap, evaluasi sebelumnya, studi riset, household survey, sector assessment, status implementasi rekomendasi, Theory of Change (Goal→Outcome→Output→Activity), budget/staffing, dan relasi antar-outcome. Skema JSON ada di dalam `evidence.html`/`planning.html` (bagian "Menunggu Data").

## Sumber data

- **Metadata threshold & rasional**: `Analisis_4_Pendekatan_Threshold_OC3_FINAL.xlsx` (sheet Data_Dasar, P1–P4, Summary_Rekomendasi, Triangulasi, Definisi_Threshold). Rekomendasi = **P2 Best Performer** (nilai AP terbaik tunggal yang nyata): OIOS 22 → 7,2% (P2; P1 10% sbg acuan resmi); OIOS 6 → 84,3%; OIOS 7 → 77,2%; OIOS 10 → 34,0%; OIOS 157 → ±80,3% (sementara); C2A.027994 → ±56,6% (sementara); OIOS 27 → ditunda (P2 tidak bermakna, baseline tidak reliabel). Nilai outlier ditandai dan ditriangulasi dgn P3/P4. Semua berlabel "usulan untuk didiskusikan".
- **Data filterabel**: unit record sheet `Indonesia_KOBO AIM_CL June 17_F` (10.620 baris, 9 AP), diagregasi per AP × wilayah × status RC (YAY09) × partisipasi (OIOS_xx_direct) × jenis kelamin memakai kolom `IND*_Num`/`IND*_Denom`. Yang di-embed ke halaman hanya agregat.
- **Bobot nasional**: HH Targeted per AP (total 64.417 HH); baseline tertimbang tervalidasi identik dengan workbook sumber (mis. OIOS 22 = 13,15%).
