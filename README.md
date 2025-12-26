<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains thousands of video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the [Laravel Partners program](https://partners.laravel.com).

### Premium Partners

- **[Vehikl](https://vehikl.com)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel)**
- **[DevSquad](https://devsquad.com/hire-laravel-developers)**
- **[Redberry](https://redberry.international/laravel-development)**
- **[Active Logic](https://activelogic.com)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).


Oke 👍 — kalau **XAMPP sudah terinstal di Kali Linux**, kamu bisa menjalankannya dengan mudah lewat terminal.
Berikut panduan lengkap dan aman step-by-step 👇

---

## 🧩 1. Pastikan XAMPP terpasang

Biasanya XAMPP terinstal di:

```bash
/opt/lampp
```

Cek dengan:

```bash
ls /opt/lampp
```

Kalau folder itu ada (berisi `lampp`, `xampp`, `htdocs`, dll), berarti XAMPP sudah benar terinstal.

---

## ▶️ 2. Menjalankan XAMPP

Gunakan perintah ini:

```bash
sudo /opt/lampp/lampp start
```

Itu akan menyalakan semua komponen utama:

* **Apache**
* **MySQL (MariaDB)**
* **ProFTPD (optional)**

Kalau berhasil, akan muncul output seperti:

```
Starting XAMPP for Linux 8.x.x...
XAMPP: Starting Apache...ok.
XAMPP: Starting MySQL...ok.
```

---

## 🛑 3. Untuk menghentikan XAMPP

Gunakan:

```bash
sudo /opt/lampp/lampp stop
```

---

## 🔁 4. Untuk restart (kalau ubah konfigurasi Apache/PHP)

```bash
sudo /opt/lampp/lampp restart
```

---

## 🧠 5. Mengecek status XAMPP

```bash
sudo /opt/lampp/lampp status
```

---

## 🌐 6. Mengakses XAMPP di browser

Buka browser dan masuk ke:

```
http://localhost
```

atau

```
http://127.0.0.1
```

Jika berhasil, akan tampil halaman dashboard XAMPP.

---

## 📁 7. Lokasi proyek web

Folder tempat kamu meletakkan file web (default):

```
/opt/lampp/htdocs/
```

Misalnya:

```bash
sudo cp -r ~/Projects/laravel-kali-test /opt/lampp/htdocs/
```

Lalu bisa diakses di browser:

```
http://localhost/laravel-kali-test/public
```

---

## ⚙️ 8. Mengatur PHP XAMPP (jika perlu)

Kalau kamu ingin XAMPP memakai PHP dari dalam `/opt/lampp/php/`, cek versi:

```bash
/opt/lampp/bin/php -v
```

Dan untuk menjalankan Composer dengan PHP XAMPP:

```bash
sudo /opt/lampp/bin/php /usr/local/bin/composer install
```

> (Pastikan path composer sesuai dengan hasil `which composer`)

---

## 💡 Tips tambahan

Kalau mau XAMPP otomatis start saat boot:

```bash
sudo ln -s /opt/lampp/lampp /etc/init.d/lampp
sudo update-rc.d lampp defaults
```

---

## Akses Mysql

```
/opt/lampp/bin/mysql -u root
```

Kalau kamu mau saya bantu **menjalankan Laravel project kamu di XAMPP (port 80 atau 8080)**, kirimkan saja struktur folder project-nya (atau path-nya) — nanti saya bantu konfigurasi virtual host atau symlink-nya biar langsung jalan di browser.


### I Try to manipulate date of commit

---

<h2>📚 Others</h2>

Berikut adalah dokumen terkait pengembangan proyek DekatKu:

  * **Project Planning:** [Google Docs - Perencanaan Sistem](https://docs.google.com/document/d/1cfyK1IEp7QWCWGjvf5Z-vEQ3a56NhXHrvp1Lzs2hAOk/edit?usp=sharing)
  * **ER Diagram (ERD):** #5
  * **Hackathon Submission:** [Imphnen Hackathon Team Page](https://hackathon.imphnen.dev/teams/a0e4ff56-888d-47d8-a0cb-4d38c6676567/submission)

---

<div align="center" style="background-color: #ffffff; padding: 20px; border-radius: 20px; width: fit-content; margin: 0 auto; box-shadow: 0 4px 6px rgba(0,0,0,0.1);">
  <h3 style="color: #333; margin-top: 0;">Supported By</h3>
  
  <div style="display: flex; gap: 25px; justify-content: center; align-items: center; flex-wrap: wrap; background-color: #efefef; padding: 10px 0;">
    <a href="https://www.facebook.com/groups/1032515944638255" target="_blank" style="display: flex; align-items: center;">
      <img src="https://hackathon.imphnen.dev/images/imphnen-logo.svg" alt="Imphnen Community" height="50"/>
    </a>
    <a href="https://www.kolosal.ai/" target="_blank" style="display: flex; align-items: center;">
      <img src="https://avatars.githubusercontent.com/u/127637382?s=200&v=4" alt="Kolosal AI" height="58" style="margin-top: -2px;"/>
    </a>
  </div>

  <p style="color: #555; margin-bottom: 0; margin-top: 15px;">
    <em>Big thanks to <b>Imphnen</b> & <b>Kolosal AI</b> for the support!</em>
  </p>
</div>
<br>

now i will try again in 30 Nov, tadi typo jir ke paste dari yutub :v

test now


readme example

```
php artisan config:clear
php artisan route:clear
php artisan cache:clear
php artisan view:clear
php artisan optimize
```


composer install for production
```
composer install --no-dev --optimize-autoloader
```
