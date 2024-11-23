# Proyek CI/CD menggunakan GitHub Actions

Proyek ini menerapkan **Continuous Integration (CI)** dan **Continuous Deployment (CD)** menggunakan GitHub Actions. Setiap kali ada perubahan pada branch `main`, pipeline akan dijalankan untuk memastikan kode diuji dan dideploy secara otomatis.

---

## **Proses CI/CD**

### **1. Continuous Integration (CI)**

Pipeline CI akan secara otomatis dijalankan setiap kali terjadi perubahan pada branch `main`. Berikut adalah tahapan dalam pipeline CI:

1. **Checkout Kode**: Mengambil versi kode terbaru dari repository menggunakan aksi `actions/checkout`.
2. **Setup Node.js**: Menyiapkan environment Node.js sesuai dengan versi yang dibutuhkan menggunakan aksi `actions/setup-node`.
3. **Instal Dependensi**: Menginstal semua dependensi proyek dengan menjalankan perintah `npm install`.
4. **Pengujian Otomatis**: Menjalankan pengujian dengan menggunakan Jest melalui perintah `npm test` untuk memastikan tidak ada bug dalam aplikasi.

---

### **2. Continuous Deployment (CD)**

Jika pipeline CI berhasil, pipeline CD akan dijalankan secara otomatis. Berikut langkah-langkah dalam proses CD:

1. **Build Aplikasi**: Membangun aplikasi menggunakan perintah `npm run build`, yang akan menghasilkan file build di folder `dist` atau sesuai konfigurasi.
2. **Deploy ke GitHub Pages**:
   - Menggunakan action `peaceiris/actions-gh-pages@v3` untuk mengunggah hasil build ke GitHub Pages.
   - Hasil build akan dipublikasikan ke branch `gh-pages`.

GitHub Pages akan menggunakan branch `gh-pages` sebagai sumber deployment, sehingga aplikasi web dapat diakses melalui URL yang disediakan oleh GitHub.

---

## **Link Hasil Deployment**

Aplikasi yang telah dideploy dapat diakses melalui GitHub Pages dengan menggunakan link berikut:  
https://gustimahardikasm.github.io/ci-cd-21060122140153-elektro/
