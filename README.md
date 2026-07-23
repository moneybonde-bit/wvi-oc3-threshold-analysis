# wvi-oc3-threshold-analysis

Threshold Analysis Platform (World Vision Indonesia). Menjelaskan dan memvisualisasikan mengapa threshold (benchmark mutu) penting sebelum penetapan target nasional, untuk 7 indikator OC3 AIM/AIM+ FY26.

## Halaman

Halaman ada di folder [`docs/`](docs/) dan dipublikasikan lewat GitHub Pages (**Settings → Pages → Deploy from a branch → `main` → `/docs`**), lalu diakses di `https://<username>.github.io/wvi-oc3-threshold-analysis/`.

Platform multi-halaman dengan navigasi global (Home · Dashboard · Opsi Threshold · Evidence · Trend TP CESP · Setting Target · Metodologi · Referensi):

- `docs/index.html` — **Home**: konsep threshold (apa itu, mengapa penting, framework Baseline → Threshold → Annual Target → Long-term Outcome) dan Key Message dengan prioritas rekomendasi **P1 → P2 → P3/P4** (utamakan P1 = standar resmi internasional bila ada; jika tidak, P2 Best Performer; P3/P4 sebagai pembanding)
- `docs/threshold-dashboard.html` — **Dashboard** (analisis): filter tersinkron, National Summary, kartu indikator dengan **threshold selector P1–P4** (ubah basis threshold live), dan detail modal berisi tabel perbandingan 4 pendekatan + **Decision Panel**. Pilihan P1–P4 per indikator **tersinkron dengan halaman Opsi Threshold** via localStorage
- `docs/evidence.html` — **Evidence Intelligence**: garis waktu bukti, kualitas data (n, 95% CI Wilson, cakupan AP, kelengkapan) & kekuatan bukti terhitung, dan Baseline Review Panel ringkas dengan penanda otomatis (detail tren per AP dipindah ke Trend TP CESP untuk menghindari duplikasi)
- `docs/cesp-trend.html` — **Trend Evaluasi TP-CESP → AIM+ (Outcome 3)**: TP-CESP FY22 Baseline → FY24 OutMon → FY25 Evaluasi + evaluasi CP sebagai pembanding tren AIM+ FY26. **Difokuskan hanya pada AP yang punya Outcome 3 (AIM+/FRS)** — 9 AP; dropdown per-AP dan tabel perbandingan tidak lagi menampilkan AP CESP lainnya. Tampilan per-AP (tren 4 titik + disagregasi Laki/Perempuan FY25 + 95% CI) DAN **tabel perbandingan antar-AP × antar-indikator** dengan filter multi-select (fokus indikator Outcome 3: Baseline · Evaluasi · AIM+). Pemetaan: CESP C3B.24689 = OIOS 6, C3B.24690 = OIOS 7, CP kekerasan fisik/psikologis = OIOS 22
- `docs/setting-target.html` — **Setting Target Outcome 3 (per AP)**: setiap AP menetapkan target indikator Outcome 3 & output. Formula (dari lembar Kompilasi): Target = baseline AIM+ FY26 ± perubahan yang ditetapkan AP (dipandu rentang), keputusan Set target vs Monitor (jika baseline sudah memenuhi threshold), sebaran per tahun fiskal FY26→FY30. Tiap indikator punya **isian sesuai sheet Kompilasi**: AP (dropdown), **Durasi (FY)** yang dapat diedit, dan **N populasi** — dari keduanya sistem menghitung **Numerator & Denominator per tahun fiskal** (Denom per FY = N populasi ÷ durasi; Num = Denom × target% FY). Ada input interaktif (slider/angka), tabel ringkasan (termasuk kolom Durasi & N populasi), dan catatan; isian tersimpan di localStorage. `docs/planning.html` kini redirect ke sini
- `docs/methodology.html` — **Metodologi**: 4 pendekatan (P1–P4) + logika pemilihan + cara perhitungan baseline
- `docs/references.html` — **Referensi**: kerangka M&E internasional + sumber data
- `docs/opsi-threshold-per-indikator.html` — **Opsi Threshold**: satu kartu per indikator (semua 7) dengan keempat kandidat P1–P4 + selector yang **tersinkron dengan dashboard**, ★ menandai rekomendasi, dan bagian **"Prioritas rekomendasi threshold: P1 → P2 → P3/P4"**. Prioritas: P1 (Literatur/OIOS, standar resmi) sebagai pilihan utama bila tersedia; bila tidak ada P1 baru gunakan P2 (Best Performer, nilai AP tunggal nyata — bisa outlier, ditriangulasi P3/P4). Rekomendasi = P1 untuk OIOS 22 & 27, P2 untuk OIOS 6/7/10/157 & C2A.027994
- `docs/ap-indicator-dashboard.html` — redirect ke `threshold-dashboard.html` (halaman lama)

### Catatan integritas data

Semua angka di platform adalah data nyata dari workbook sumber — tidak ada data yang dikarang. Selisih antar-fase (TP-CESP vs AIM+) dapat mencerminkan perbedaan instrumen/sampel dan ditandai untuk ditafsirkan hati-hati. Isian target-setting per AP tersimpan lokal di browser (localStorage), bukan di server.

## Sumber data

- **Metadata threshold & rasional**: `Analisis_4_Pendekatan_Threshold_OC3_FINAL.xlsx` (sheet Data_Dasar, P1–P4, Summary_Rekomendasi, Triangulasi, Definisi_Threshold). Prioritas rekomendasi = **P1 → P2 → P3/P4** (utamakan P1 bila ada; jika tidak, P2 Best Performer): OIOS 22 → **P1 10%** (standar resmi OIOS; P2 7,2% sbg pembanding); OIOS 27 → **P1 10%** (standar resmi OIOS; P2 tidak bermakna karena baseline mendekati nol); OIOS 6 → **P2 84,3%**; OIOS 7 → **P2 77,2%**; OIOS 10 → **P2 34,0%**; OIOS 157 → **P2 ±80,3%** (sementara); C2A.027994 → **P2 ±56,6%** (sementara). Nilai P2 outlier ditandai dan ditriangulasi dgn P3/P4. Semua berlabel "usulan untuk didiskusikan".
- **Data filterabel**: unit record sheet `Indonesia_KOBO AIM_CL June 17_F` (10.620 baris, 9 AP), diagregasi per AP × wilayah × status RC (YAY09) × partisipasi (OIOS_xx_direct) × jenis kelamin memakai kolom `IND*_Num`/`IND*_Denom`. Yang di-embed ke halaman hanya agregat.
- **Bobot nasional**: HH Targeted per AP (total 64.417 HH); baseline tertimbang tervalidasi identik dengan workbook sumber (mis. OIOS 22 = 13,15%).
- **Tren TP-CESP (fase sebelumnya)**: `National_BaselineOutcome_MonitoringEvaluation_CESP_Result_FY22FY25.xlsx` (sheet Table9 → Baseline FY22 + OutMon FY24 per AP per indikator dengan 95% CI; sheet Data_CESP_Evaluation_FY25 → Evaluasi FY25 per AP dengan disagregasi Boys/Girls) dan `CP.xlsx` (evaluasi Child Protection, 7 AP + Nasional, dengan Boys/Girls). Dipetakan ke indikator AIM+ (OIOS 6/7/22) untuk membentuk tren hingga FY26.
- **Setting Target**: `OC_2_draft_concept_setting_target_1.xlsx` (sheet Kompilasi) — formula & rentang perubahan, threshold per indikator (P2 best-performer untuk OIOS 6/7/10; OIOS 10% untuk 22/27), durasi FY, N populasi, breakdown Numerator/Denominator per tahun. Halaman Setting Target menyediakan isian kosong untuk kolom Kompilasi (AP, durasi, N populasi) dan menghitung Numerator/Denominator per FY. Baseline per-AP diambil dari agregasi unit record AIM+ FY26.
