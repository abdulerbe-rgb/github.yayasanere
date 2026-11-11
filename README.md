# ERBE AI Agent — Integrated Foundation Management System

Asisten operasional digital Yayasan ERBE (Education, Religion, Bee, Entertainment) untuk mengelola relawan, program, dokumentasi, laporan donatur, dan media sosial.

## Modul
1. Dashboard: statistik relawan, kegiatan, donatur, dan konten.
2. Relawan: registrasi, kontak, keahlian, ketersediaan, penugasan, kehadiran, jam kontribusi, pelatihan, evaluasi.
3. Program & kegiatan: rencana kerja, tujuan, jadwal, lokasi, PIC, peserta, indikator, output, outcome, kendala, tindak lanjut.
4. Dokumentasi: foto/video, keterangan, tanggal, lokasi, persetujuan penggunaan, tautan arsip.
5. Laporan donatur: ringkasan eksekutif, latar belakang, tujuan, pelaksanaan, penerima manfaat terverifikasi, output/outcome, anggaran aktual, bukti, pembelajaran, tindak lanjut.
6. Donor relations: profil lembaga/individu, minat dukungan, riwayat komunikasi, kontribusi, ucapan terima kasih, jadwal laporan.
7. Social media: kalender konten, pilar konten, caption, carousel, skrip Reels, CTA, status draf/review/disetujui/terbit.
8. AI Assistant: membantu merangkum data, menulis draf, menyusun laporan, caption, surat, proposal, dan daftar tindak lanjut.

## Alur kerja inti
Input kegiatan sekali → lengkapi data dan bukti → AI menyiapkan draf laporan donatur dan konten sosial media → penanggung jawab memverifikasi fakta, angka, anggaran, serta izin → admin menyetujui → pengiriman/publikasi melalui kanal resmi → arsip dan audit log.

## Arsitektur yang disarankan
- Frontend: HTML/CSS/JavaScript (atau React setelah kebutuhan stabil).
- Backend: Node.js API atau Google Apps Script untuk pilot.
- Database: Supabase/PostgreSQL; Google Sheets hanya untuk pilot sederhana.
- AI: OpenAI API atau Gemini API melalui backend.
- Otomasi: n8n.
- File: Google Drive dengan kontrol akses.
- Kanal: Gmail, WhatsApp Business Platform, Meta Graph API (tergantung izin dan kelayakan akun).

## Keamanan & tata kelola
- API key hanya di backend/secret manager, tidak pernah di browser.
- Login dan role: Super Admin, Admin Program, Koordinator Relawan, Keuangan, Komunikasi, Viewer/Donatur (jika dibutuhkan).
- Terapkan least privilege, audit log, backup, persetujuan manusia, dan kebijakan retensi.
- Data anak dan penerima manfaat sangat dilindungi: minimalkan data, samarkan identitas, batasi akses, jangan unggah data sensitif ke AI tanpa dasar dan perlindungan memadai.
- Foto, video, dan testimoni hanya digunakan setelah persetujuan yang sesuai.
- AI dilarang mengarang angka, dampak, testimoni, tanggal, dan nominal. Informasi yang belum ada ditandai [PERLU DILENGKAPI].
- Tidak ada pengiriman pesan atau publikasi otomatis sebelum persetujuan admin.

## Urutan pengembangan
Fase 1: dashboard dan database relawan/kegiatan/donatur/konten.
Fase 2: laporan dan generator konten berbasis data.
Fase 3: autentikasi, role, database terpusat, penyimpanan file, audit log.
Fase 4: AI API dan integrasi n8n.
Fase 5: Gmail, WhatsApp Business, Meta Graph API setelah akses resmi tersedia.

## Status
Repository ini adalah fondasi proyek. Integrasi AI, database bersama, dan kanal eksternal memerlukan konfigurasi akun, kredensial, dan deployment. Jangan menyebut prototipe sebagai sistem produksi sebelum pengujian keamanan dan operasional selesai.
