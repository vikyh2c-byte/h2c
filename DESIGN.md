# DESIGN SYSTEM SPECIFICATION: H2C WISATA MANDIRI
**Archetype:** High-Trust Studio Editorial & Functional Clarity  
**Synthesis:** Linear (Craft & Precision) + Mobbin (Editorial White & Content-First) + Wise (Fintech Trust & Radical Transparency)  
**Target:** Anti-AI Slop UI/UX Redesign  
**Entity:** PT. HDUAC Berkah Mandiri (Izin Resmi Kemenag PPIU No. 26032300175410003)

---

## 1. Executive Summary & Design Manifesto

### 1.1 Problem Statement: AI Slop vs. High-Trust Editorial
Antarmuka agen perjalanan umroh daring saat ini kerap terjebak dalam perangkap klise "AI Slop Luxury":
- Tipografi serif berlebihan (*Playfair Display*, *Cormorant Garamond*) yang tampak dipaksakan dan sulit dibaca pada layar seluler.
- Gradasi warna emas murahan (`#c5a059`, `#dfba73`) dengan *text-shadow* dan *glow effect* yang mengaburkan legitimasi institusional.
- Avatar lingkaran dengan inisial dua huruf generik (AK, MM, TL) alih-alih menampilkan pembimbing ibadah riil.
- Ornamen dekoratif tidak fungsional (pola kisi-kisi SVG Arabesque, kubah palsu, divider floral, pita mengilap).
- Spam badge tidak berdasar (*"Kepemimpinan Amanah"*, *"Layanan No. 1 Se-Indonesia"*).
- Penjajaran teks tengah (*center-aligned text*) di mana-mana yang merusak keterbacaan paragraf panjang.

### 1.2 The New Paradigm: Linear + Mobbin + Wise
H2C Wisata Mandiri mengadopsi standar desain produk digital kelas dunia untuk membangun otoritas, legitimasi hukum, dan rasa tenang bagi calon jamaah:
1. **Linear (Precision Craftsmanship):**
   - Garis batas setipis rambut (*hairline borders* 1px `slate-200`).
   - Kontras mikro tajam antara latar belakang kanvas dan permukaan kartu.
   - Tipografi sans-serif teknis dengan *letter-spacing* rapat (*tight tracking*).
   - Indikator status presisi (dot hijau live/verified, metadata tabular).
2. **Mobbin (Gallery-White & Content-First Hierarchy):**
   - Kanvas monokrom putih bersih (`#ffffff` dan `#f8fafc`).
   - Geometri kartu *squircle* presisi (`rounded-2xl` dan `rounded-xl`).
   - Pill navigasi dan filter berbentuk stadium (`rounded-full`).
   - Dokumentasi fotografi nyata dengan rasio aspek konsisten (16:10, 4:3, 1:1) berbingkai *hairline*.
3. **Wise (Radical Transparency & Financial Trust):**
   - Struktur perbandingan berdampingan (*head-to-head comparison matrix*).
   - Pemisahan rincian biaya secara transparan: hotel, visa, tiket pesawat, bimbingan, asuransi (tanpa tanda bintang `*` atau biaya tersembunyi).
   - Tanda legalitas PPIU Kemenag dan rekening giro bank resmi tervalidasi sebagai jangkar kepercayaan utama (*trust anchor*).

---

## 2. Color System & Surface Hierarchy

Sistem warna dirancang strictly monokromatik fungsional. Warna aksen tunggal hanyalah **Emerald Fungsional** sebagai penanda verifikasi dan tombol konversi utama. **Dilarang keras memakai gradasi emas, efek kilau logam, atau aksen kuning.**

### 2.1 Color Palette Matrix

| Peran Token | Nilai Hex | Tailwind Class | Penggunaan Utama |
| :--- | :--- | :--- | :--- |
| **Canvas Primary** | `#ffffff` | `bg-white` | Latar utama halaman, body, kartu elevated |
| **Canvas Subtle / Secondary** | `#f8fafc` | `bg-slate-50` | Latar selang-seling section, table row alternate, background input |
| **Surface Raised / Muted** | `#f1f5f9` | `bg-slate-100` | Badge background, chip inactive, skeleton loader |
| **Hairline Border** | `#e2e8f0` | `border-slate-200` | Batas antar kartu, divider tabel, header bottom border |
| **Hairline Border Hover** | `#94a3b8` | `hover:border-slate-400` | State interaktif kartu dan field formulir |
| **Text Heading / Primary** | `#0f172a` | `text-slate-900` | H1, H2, H3, label harga, nama asatidz, metrik utama |
| **Text Body / Secondary** | `#475569` | `text-slate-600` | Paragraf penjelasan, detail fasilitas, rincian itinerary |
| **Text Muted / Tertiary** | `#64748b` | `text-slate-500` | Deskripsi tambahan, metadata tanggal, label form, catatan kaki |
| **Text Subtle / Disabled** | `#94a3b8` | `text-slate-400` | Placeholder, breadcrumb non-aktif, disclaimer legal minor |
| **Accent Emerald (Primary)** | `#047857` | `bg-emerald-700` / `text-emerald-700` | Tombol CTA utama, badge status resmi, icon checklist verifikasi |
| **Accent Emerald Hover** | `#065f46` | `hover:bg-emerald-800` | State hover tombol aksi utama |
| **Accent Emerald Soft** | `#ecfdf5` | `bg-emerald-50` | Latar badge "PPIU Kemenag Resmi", alert verified status |
| **Accent Emerald Border** | `#a7f3d0` | `border-emerald-200` | Batas badge verified status |

### 2.2 Aturan Kontras & Permukaan
- **Rasio Kontras Minimum:** Seluruh teks memiliki rasio kontras terhadap latar belakang minimal 4.5:1 (WCAG AA) dan 7:1 untuk teks paragraf panjang (WCAG AAA).
- **Elevasi Tanpa Drop Shadow Berat:** Hindari shadow berdimensi besar (`shadow-2xl` bergaya AI slop). Gunakan border 1px `border-slate-200` dikombinasikan dengan bayangan studio sangat halus:
  ```css
  /* Studio Subtle Base */
  box-shadow: 0 1px 2px 0 rgba(15, 23, 42, 0.05);
  /* Studio Hover Elevation */
  box-shadow: 0 10px 25px -5px rgba(15, 23, 42, 0.04), 0 8px 10px -6px rgba(15, 23, 42, 0.02);
  ```

---

## 3. Typography Architecture

Strictly **Modern Sans-serif Presisi**. Nol toleransi untuk font serif ornamental (*Playfair Display*, *Cormorant Garamond*, *Georgia*).

### 3.1 Typefaces
- **Primary:** `Plus Jakarta Sans` (Geometric, clean, modern Indonesian-friendly character set).
- **Secondary Fallback:** `Inter` (UI technical standard), `-apple-system`, `system-ui`, `sans-serif`.
- **Numeric Figures:** Wajib menggunakan kelas Tailwind `tabular-nums` untuk angka harga, nomor PPIU, kapasitas kursi, dan tanggal keberangkatan agar lebar karakter seragam dan mudah dipindai mata (*scannable*).

### 3.2 Typographic Hierarchy & Classes

| Tingkat Hierarki | Ukuran / Leading | Weight | Tracking | Kelas Tailwind |
| :--- | :--- | :--- | :--- | :--- |
| **Display H1 (Hero)** | 48px – 64px (`leading-[1.1]`) | Bold (700) / Extrabold (800) | `-0.03em` | `text-4xl sm:text-5xl lg:text-6xl font-extrabold tracking-tight text-slate-900` |
| **Section Title H2** | 28px – 36px (`leading-tight`) | Bold (700) | `-0.02em` | `text-2xl sm:text-3xl lg:text-4xl font-bold tracking-tight text-slate-900` |
| **Card / Item H3** | 18px – 22px (`leading-snug`) | Semibold (600) | `-0.015em` | `text-lg sm:text-xl font-semibold tracking-tight text-slate-900` |
| **Subhead / Lead Body**| 16px – 18px (`leading-relaxed`)| Regular (400) / Medium (500)| Normal | `text-base sm:text-lg text-slate-600 leading-relaxed` |
| **Regular Body** | 14px – 16px (`leading-relaxed`)| Regular (400) | Normal | `text-sm sm:text-base text-slate-600 leading-relaxed` |
| **Tabular Numbers / Pricing** | 24px – 36px (`leading-none`) | Bold (700) | `-0.02em` | `text-2xl sm:text-3xl font-bold tracking-tight tabular-nums text-slate-900` |
| **Metadata / Microcopy** | 12px – 13px (`leading-normal`)| Medium (500) | `+0.01em` | `text-xs font-medium text-slate-500 tracking-normal` |
| **Status Pill / Badge** | 11px – 12px (`leading-none`) | Semibold (600) | `+0.02em` | `text-xs font-semibold tracking-wide uppercase` |

---

## 4. Layout, Geometry & Spacing Rules

Mengadaptasi presisi teknis **Linear** dan kejelasan galeri **Mobbin**.

### 4.1 Geometri Kontainer
- **Pill Stadium:** `rounded-full` khusus untuk tombol filter, tag status sertifikasi, dan badge navigasi.
- **Card Containers:** `rounded-2xl` (16px – 20px) atau `rounded-xl` (12px) dengan `border border-slate-200 bg-white`.
- **Inner Elements / Media:** `rounded-xl` (12px) untuk thumbnail foto, video preview, dan input field.
- **Button Radius:** `rounded-xl` untuk tombol aksi fungsional (bukan pill bulat tebal klise yang memakan ruang vertikal).

### 4.2 Grid & Breakpoint System
- **Max Width Container:** `max-w-7xl` (1280px) untuk layout studio terbuka dengan padding horizontal:
  - Mobile: `px-4 sm:px-6`
  - Desktop: `lg:px-8`
- **Vertical Spacing:**
  - Antar Section: `py-16 sm:py-24` (lapang, bersih, memberikan ruang bernapas editorial).
  - Antar Elemen dalam Section: `gap-6` hingga `gap-8`.

---

## 5. Component Specifications (Anti-AI Slop Blueprint)

### 5.1 Top Navigation Bar (Header Studio)
- **Struktur:** Sticky bar tipis dengan efek kaca presisi `bg-white/90 backdrop-blur-md border-b border-slate-200/80 sticky top-0 z-50`.
- **Elemen:**
  1. Logo H2C presisi (vektor jernih tanpa bayangan atau kilau gradasi).
  2. Pill Status Legalitas Aktif: `inline-flex items-center gap-1.5 px-3 py-1 bg-emerald-50 border border-emerald-200 text-emerald-700 text-xs font-semibold rounded-full`.
  3. Navigasi Teks: Link horizontal warna `text-slate-600 hover:text-slate-900 text-sm font-medium transition-colors`.
  4. CTA Kanan: Tombol solid `bg-emerald-700 text-white hover:bg-emerald-800 text-xs sm:text-sm font-semibold px-4 py-2 rounded-xl transition-all shadow-sm`.

### 5.2 Hero Section (Mobbin Editorial Split)
- **Komposisi:** Asimetris 2 kolom (Left: Editorial Title & Value Prop, Right: Live Status Frame / Clean Aspect Ratio Media).
- **Left Column:**
  - Kicker Pill: `RESMI TERDAFTAR KEMENAG RI PPIU NO. 26032300175410003` dengan dot hijau berkedip halus (`animate-pulse`).
  - H1 Headline: *"Ibadah Umroh Presisi, Terbimbing Sunnah, Tanpa Biaya Tersembunyi."*
  - Body: *"Biro perjalanan ibadah berizin resmi Kemenag RI dengan kepastian jadwal, hotel dekat pelataran masjid, bimbingan sunnah shahih, dan transparansi rincian biaya sejak awal pendaftaran."*
  - Action Group:
    - Primary CTA: Tombol Konsultasi WhatsApp / Cek Ketersediaan Seat (`bg-emerald-700 hover:bg-emerald-800 text-white rounded-xl px-6 py-3 font-semibold`).
    - Secondary Action: Tombol Unduh Itinerary Lengkap (PDF) atau Tautan Cek SIMPU Kemenag (`border border-slate-200 hover:border-slate-400 bg-white text-slate-700 rounded-xl px-6 py-3 font-medium`).
- **Trust Strip Langsung (Inline Trust Bar):**
  - 4 pilar ringkas dengan border hairline:
    1. **Izin PPIU No. 26032300175410003** (Tervalidasi Kemenag RI)
    2. **Akreditasi A Kemenag** (Standar Mutu Pelayanan Tertinggi)
    3. **Rekening Giro Resmi PT** (Bank BSI a.n. PT HDUAC Berkah Mandiri)
    4. **Kantor Fisik Riil** (Semarang & Bekasi)

### 5.3 Paket & Pricing Cards (Wise Radical Transparency Model)
- **Prinsip Anti-Slop:** Tidak ada kata "Harga Mulai Dari" yang menjebak tanpa rincian. Semua angka ditulis riil dengan `tabular-nums`.
- **Struktur Kartu:**
  - Container: `border border-slate-200 rounded-2xl bg-white p-6 sm:p-8 hover:border-slate-400 transition-all shadow-sm`.
  - Header: Nama Paket (cth: "Paket Umroh Reguler 12 Hari Musim 2026/2027"), badge kategori ("Executive" / "Quad Seat").
  - Price Tag: `Rp 33.500.000` (`text-3xl font-bold tracking-tight text-slate-900 tabular-nums`) + keterangan *"All-in tanpa biaya siluman"*.
  - Rincian Transparan (Tabel / List Spesifikasi Bergaris):
    - **Maskapai:** Saudia Airlines / Garuda Indonesia (Direct Flight CGK-JED / KNO-MED).
    - **Hotel Makkah:** Bintang 5 (±50m pelataran Masjidil Haram).
    - **Hotel Madinah:** Bintang 4/5 (±100m pelataran Masjid Nabawi).
    - **Transportasi:** Kereta Cepat Haramain High-Speed Train Makkah-Madinah.
    - **Termasuk:** Visa Umroh resmi, Asuransi Perjalanan Syariah, Muthowif Mukim Berpengalaman, Perlengkapan Eksklusif, Manasik Intensif.
    - **Bebas Biaya Tak Terduga:** Handling airport domestik & Saudi sudah termasuk.
  - CTA Card: Tombol booking berlabel jelas `Pilih Paket Ini & Kunci Kursi`.

### 5.4 Matriks Perbandingan Terbuka (Wise Style Head-to-Head Table)
Tabel perbandingan native HTML yang bersih dan jujur, memperlihatkan perbedaan standar H2C vs Travel Konvensional:

```html
<div class="overflow-x-auto border border-slate-200 rounded-2xl">
  <table class="w-full text-left text-sm text-slate-600">
    <thead class="bg-slate-50 text-slate-900 font-semibold border-b border-slate-200">
      <tr>
        <th class="py-4 px-6">Parameter Layanan</th>
        <th class="py-4 px-6 text-emerald-700 bg-emerald-50/50">H2C Wisata Mandiri (PT HDUAC)</th>
        <th class="py-4 px-6">Travel Konvensional / Umum</th>
      </tr>
    </thead>
    <tbody class="divide-y divide-slate-200">
      <tr class="hover:bg-slate-50/50">
        <td class="py-4 px-6 font-medium text-slate-900">Legalitas PPIU</td>
        <td class="py-4 px-6 text-emerald-800 font-medium bg-emerald-50/20">Resmi SK Kemenag No. 26032300175410003</td>
        <td class="py-4 px-6 text-slate-500">Seringkali sub-konsorsium / pinjam bendera</td>
      </tr>
      <tr class="hover:bg-slate-50/50">
        <td class="py-4 px-6 font-medium text-slate-900">Rekening Pembayaran</td>
        <td class="py-4 px-6 text-emerald-800 font-medium bg-emerald-50/20">Giro Bank BSI a.n. PT HDUAC Berkah Mandiri</td>
        <td class="py-4 px-6 text-slate-500">Sering transfer ke rekening pribadi/owner</td>
      </tr>
      <tr class="hover:bg-slate-50/50">
        <td class="py-4 px-6 font-medium text-slate-900">Kepastian Jarak Hotel</td>
        <td class="py-4 px-6 text-emerald-800 font-medium bg-emerald-50/20">Tertulis di kontrak (50–150m dari pelataran)</td>
        <td class="py-4 px-6 text-slate-500">Klaim "bintang 5" tapi jarak 800m+ naik shuttle</td>
      </tr>
      <tr class="hover:bg-slate-50/50">
        <td class="py-4 px-6 font-medium text-slate-900">Rute Perjalanan Darat</td>
        <td class="py-4 px-6 text-emerald-800 font-medium bg-emerald-50/20">Kereta Cepat Haramain (2 jam 20 menit)</td>
        <td class="py-4 px-6 text-slate-500">Bus umum antar kota (6–8 jam melelahkan)</td>
      </tr>
      <tr class="hover:bg-slate-50/50">
        <td class="py-4 px-6 font-medium text-slate-900">Biaya Tambahan</td>
        <td class="py-4 px-6 text-emerald-800 font-medium bg-emerald-50/20">All-in transparan, zero hidden fees</td>
        <td class="py-4 px-6 text-slate-500">Handling, asuransi, dan tipping ditagih susulan</td>
      </tr>
    </tbody>
  </table>
</div>
```

### 5.5 Pembimbing & Manajemen (Authentic Editorial Showcase)
- **Larangan Keras:** Dilarang keras menggunakan avatar inisial bulat kartun (AK, MM, TL) atau stock photo model luar negeri.
- **Spesifikasi:**
  - Kartu foto potret rasio 4:5 atau 1:1 tajam dengan sudut `rounded-xl`.
  - Foto riil asatidz pembimbing dan pimpinan biro berpakaian rapi di Tanah Suci atau studio profesional.
  - Keterangan kredibilitas: Nama lengkap dan gelar akademis/syariah, rekam jejak bimbingan manasik, sertifikasi pembimbing ibadah Kemenag/BNSP.

### 5.6 Galeri & Dokumentasi Keberangkatan (Mobbin Clean Gallery)
- **Komposisi:** Grid 3 atau 4 kolom dengan foto dokumentasi riil jamaah H2C.
- **Rasio Aspek Media:** Rasio 16:10 atau 4:3 dengan `border border-slate-200 rounded-xl overflow-hidden`.
- **Caption Fungsional:** Menampilkan bulan keberangkatan, lokasi riil (Pelataran Masjid Nabawi, Lounge Umroh Soekarno-Hatta, Stasiun Kereta Cepat Haramain).

### 5.7 Trust Signals & Akuntabilitas Hukum (Wise Security Section)
Blok akuntabilitas legalitas tingkat tinggi sebelum footer:
1. **Verifikasi Kemenag Langsung:** Tautan outbound resmi ke portal SIMPU Kemenag RI dengan instruksi verifikasi mandiri nomor SK PPIU `26032300175410003`.
2. **Akun Bank Terverifikasi:**
   - Bank: Bank Syariah Indonesia (BSI)
   - Atas Nama: **PT HDUAC Berkah Mandiri**
   - Himbauan tegas: *"Kami tidak pernah memungut biaya melalui rekening perorangan atau dompet digital pribadi."*
3. **Kantor Fisik Nyata:**
   - **Kantor Operasional Cabang Semarang:** Semarang, Jawa Tengah (pusat layanan pendaftaran regional, konsultasi jamaah, dan penyerahan dokumen/paspor).
   - **Kantor Pusat:** Ruko Telaga Pesona Blok L3 No. 3 & 5, Cikarang Barat, Kabupaten Bekasi, Jawa Barat.
   - Peta interaktif atau tautan Google Maps yang terverifikasi.

### 5.8 Footer (Linear Craftsmanship & Legal Foundations)
- **Latar:** Monokrom pekat `bg-slate-900 text-slate-300 border-t border-slate-800 py-16`.
- **Hierarki:**
  - Brand & Legal Entity: **H2C Wisata Mandiri** — Unit Bisnis Perjalanan Ibadah PT. HDUAC Berkah Mandiri.
  - Nomor PPIU: `Kemenag RI No. 26032300175410003`.
  - Tautan Hukum Wajib: Syarat & Ketentuan Layanan, Kebijakan Privasi, Kebijakan Pembatalan & Pengembalian Dana (*Refund Policy*).
  - Copyright: `© 2026 PT HDUAC Berkah Mandiri. Hak Cipta Dilindungi Undang-Undang.`

---

## 6. Strict Anti-Gimmick Rules (Zero Tolerance for AI Slop)

| Trik AI Slop / Manipulatif | Status | Alasan | Implementasi Beretika H2C |
| :--- | :--- | :--- | :--- |
| **Fake Countdown Timer** (cth: "00:14:59 tersisa!") | **DILARANG** | Merusak integritas syar'i dan tampak seperti penipuan daring (*scam*). | Tampilkan jadwal bulan keberangkatan riil dan batas waktu administratif penutupan visa. |
| **Fake Social Proof Toasts** (cth: *"Ibu Ratna dari Bandung baru saja mendaftar"*) | **DILARANG** | Pemalsuan data interaksi pengguna. | Tampilkan kuota sisa kursi riil yang diperbarui berkala via database/admin. |
| **Gold Gradient & Metallic Shimmer Text** | **DILARANG** | Visual murahan yang menurunkan kredibilitas institusi resmi. | Warna teks monokrom pekat `text-slate-900` dengan tipografi sans-serif presisi. |
| **Initial Avatar Badges** (AK, MM) | **DILARANG** | Tanda khas template bot/AI yang tidak memiliki aset riil. | Wajib foto riil pembimbing atau kartu informasi institusional. |
| **Badge Spam & Slogan Klise** (10+ badge bintang emas bertumpuk) | **DILARANG** | Menimbulkan kecurigaan calon jamaah dan mengaburkan informasi penting. | Gunakan 4 pilar verifikasi legalitas faktual (PPIU, Akreditasi, BSI, Kantor Fisik). |
| **Video Autoplay Bersuara** | **DILARANG** | Mengganggu calon jamaah yang mengakses dari ruang publik/kantor. | Seluruh video dokumentasi default `muted` dengan tombol kontrol jelas. |

---

## 7. Tailwind CSS Configuration Blueprint

Konfigurasi ekstensi tema yang siap diintegrasikan pada project:

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./index.html",
    "./admin.html",
    "./**/*.{html,js}"
  ],
  theme: {
    extend: {
      colors: {
        slate: {
          50: '#f8fafc',
          100: '#f1f5f9',
          200: '#e2e8f0',
          300: '#cbd5e1',
          400: '#94a3b8',
          500: '#64748b',
          600: '#475569',
          700: '#334155',
          800: '#1e293b',
          900: '#0f172a',
          950: '#020617',
        },
        emerald: {
          50: '#ecfdf5',
          100: '#d1fae5',
          200: '#a7f3d0',
          600: '#059669',
          700: '#047857',
          800: '#065f46',
          900: '#064e3b',
        }
      },
      fontFamily: {
        sans: ['"Plus Jakarta Sans"', 'Inter', 'system-ui', '-apple-system', 'sans-serif'],
      },
      letterSpacing: {
        tighter: '-0.04em',
        tight: '-0.02em',
        normal: '0em',
        wide: '0.02em',
      },
      borderRadius: {
        'xl': '12px',
        '2xl': '16px',
        '3xl': '24px',
        'full': '9999px',
      },
      boxShadow: {
        'studio-subtle': '0 1px 2px 0 rgba(15, 23, 42, 0.05)',
        'studio-card': '0 4px 6px -1px rgba(15, 23, 42, 0.05), 0 2px 4px -2px rgba(15, 23, 42, 0.05)',
        'studio-hover': '0 12px 24px -4px rgba(15, 23, 42, 0.08), 0 4px 6px -2px rgba(15, 23, 42, 0.03)',
      }
    }
  },
  plugins: []
}
```

---

## 8. Implementation & Quality Audit Checklist

Gunakan checklist ini untuk mengaudit setiap komponen sebelum perilisan:

- [ ] **Zero AI Slop:** Tidak ada font serif (*Playfair Display* / *Cormorant Garamond*), tidak ada gradasi emas, tidak ada avatar inisial (AK, MM).
- [ ] **Typography Rigor:** Seluruh heading menggunakan `Plus Jakarta Sans` dengan `tracking-tight` dan kontras `text-slate-900`.
- [ ] **Tabular Numerics:** Seluruh nominal harga, tanggal, nomor SK PPIU, dan kuota kursi menggunakan kelas `tabular-nums`.
- [ ] **Functional Accent Only:** Warna hijau hanya digunakan pada status terverifikasi (`emerald-50`/`emerald-700`) dan tombol aksi utama.
- [ ] **Hairline Borders:** Seluruh kartu dan sekat section menggunakan `border-slate-200` setipis 1px.
- [ ] **Wise-Style Transparency:** Tersedia tabel perbandingan transparan head-to-head H2C vs Travel Umum.
- [ ] **Real Proof of Entity:** SK PPIU No. 26032300175410003, tautan verifikasi SIMPU Kemenag, Rekening BSI a.n. PT HDUAC Berkah Mandiri, dan alamat kantor Semarang & Bekasi tercantum akurat.
- [ ] **Performance & Accessibility:** Tidak ada aset SVG berat atau animasi berlebih, mobile tap-target minimal 44x44px, kontras WCAG AA/AAA terpenuhi.
