# KasirKu — paket siap konversi APK

Isi: prototipe kasir offline + konfigurasi Capacitor Android + workflow cloud untuk membangun APK debug.

## Build lokal (laptop/PC)
1. Install Node.js LTS dan Android Studio (dengan Android SDK).
2. Ekstrak folder ini.
3. Buka terminal di folder proyek dan jalankan:
   ```bash
   npm install
   npx cap add android
   npx cap sync android
   npx cap open android
   ```
4. Di Android Studio: tunggu Gradle sync, pilih Build > Build Bundle(s) / APK(s) > Build APK(s).
5. APK debug biasanya ada di `android/app/build/outputs/apk/debug/app-debug.apk`.

## Build melalui GitHub Actions
1. Buat repository GitHub dan upload semua isi folder ini.
2. Buka tab Actions, pilih workflow **Build KasirKu APK**, lalu tekan **Run workflow**.
3. Setelah workflow selesai, buka hasil run dan unduh artifact `KasirKu-debug-apk`.

Workflow membangun APK debug untuk uji coba, bukan APK release bertanda tangan untuk distribusi publik.

## Catatan prototipe
- Data disimpan di browser storage/WebView perangkat. Jangan hapus data aplikasi jika ingin mempertahankan transaksi.
- Fitur ini belum memiliki backup otomatis, sinkronisasi cloud, printer Bluetooth, atau QRIS dinamis.
- Uji transaksi dan ekspor data terlebih dahulu sebelum digunakan untuk pencatatan usaha penting.
