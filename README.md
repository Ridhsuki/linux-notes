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


```
php artisan config:clear
php artisan route:clear
php artisan cache:clear
php artisan view:clear
php artisan optimize:clear

```

# 1. Install necessary tools (if not already present)
sudo apt update && sudo apt install hostapd dnsmasq create_ap

# 2. Stop services temporarily (optional, but good practice)
sudo systemctl stop hostapd dnsmasq

# 3. Start the hotspot (replace wlan1 with your AP interface, eth0 with your internet source)
# Example: Create hotspot named 'MyKaliHotspot' with password 'mypassword123'
sudo create_ap wlan1 eth0 MyKaliHotspot mypassword123

# To stop it, press Ctrl+C in the terminal where create_ap is running.


composer install for production
```
composer install --no-dev --optimize-autoloader
```
```
composer install --no-dev --optimize-autoloader --no-interaction --prefer-dist
```


Ini **kejadian khas Kali Linux** 👍
Masalahnya **bukan command‑nya salah**, tapi **shell yang kamu pakai bukan bash**.

👉 **Kali Linux default pakai `zsh`**, bukan `bash`
Dan di **zsh**, `history -c` / `history -w` **memang nggak ada**, makanya keluar error:

```
fc: event not found: -c
```

---

## ✅ Cara clear history di Kali Linux (ZSH)

### 1️⃣ Clear history session + file (AMAN & RECOMMENDED)

Jalankan ini:

```bash
rm ~/.zsh_history
history -p
```

Lalu **tutup terminal dan buka lagi**.

✔️ Ini benar‑benar hapus history
✔️ Cocok buat Kali / zsh

---

### 2️⃣ Clear history tanpa logout (langsung bersih)

```bash
rm ~/.zsh_history
fc -p
```

`fc -p` = reset history stack di zsh

---

### 3️⃣ Clear history & stop logging sementara

Kalau mau **session ini nggak nyimpan history sama sekali**:

```bash
unset HISTFILE
rm ~/.zsh_history
```

⚠️ Setelah ini, command kamu **tidak akan disimpan** sampai terminal ditutup.

---

## 🔍 Cek kamu pakai shell apa

Biar yakin:

```bash
echo $SHELL
```

Kalau hasilnya:

* `/usr/bin/zsh` → pakai cara di atas ✅
* `/bin/bash` → baru pakai `history -c`

---

## 🧠 Kenapa error `fc: event not found` muncul?

Karena di **zsh**:

* `history` ≠ `bash history`
* `-c` dan `-w` dianggap **event**, bukan option

Makanya zsh bilang:

> “event `-c` tidak ditemukan”

---

## ✅ TL;DR (jawaban singkat)

Di Kali Linux (zsh):

```bash
rm ~/.zsh_history
fc -p
```

Tutup terminal → buka lagi → **history bersih total** 🧼

---

Kalau kamu mau:

* clear history **tanpa root**
* clear history **untuk forensics hygiene**
* atau **permanently disable history di Kali**

bilang aja, aku jelasin level‑by‑level 🔥


Ini versi yang jauh lebih simpel, berfokus hanya pada kendali terminal:

---

### 🟢 Menjalankan RustDesk (Saat Ingin Remote)

Cukup buka lewat menu aplikasi (GUI) atau ketik di terminal:

```bash
rustdesk

```

*(Tidak perlu menjalankan service sistem jika hanya ingin remote keluar).*

---

### 🔴 Mematikan Total & Hapus Ikon Topbar

Gunakan ini setelah selesai pakai agar Kali bersih kembali:

```bash
sudo pkill rustdesk

```

---

### 🛡️ Pengaturan Service (Background)

Gunakan ini untuk mengatur apakah RustDesk boleh berjalan otomatis atau tidak:

* **Matikan Auto-Start (Sangat Disarankan):**
Agar RustDesk tidak jalan sendiri saat laptop baru nyala.
```bash
sudo systemctl disable rustdesk

```


* **Nyalakan Jika Ingin Di-Remote dari Windows:**
Wajib dijalankan jika laptop Kali kamu yang mau dikontrol dari jauh.
```bash
sudo systemctl start rustdesk

```


* **Matikan Service Saat Ini:**
```bash
sudo systemctl stop rustdesk

```



---

### 📝 Ringkasan Cepat:

1. **Mau Remote Windows?** Buka aplikasi → Pakai → `sudo pkill rustdesk` (selesai).
2. **Mau Di-Remote Windows?** `sudo systemctl start rustdesk` → Berikan ID ke teman.
3. **Ikon Topbar Ganggu?** `sudo pkill rustdesk`.

Ada lagi perintah spesifik yang ingin kamu buatkan shortcut-nya?


### Others Resource
#### Best 
- _Cooming Soon_
#### Not Bad
- https://github.com/U171N/perintah-linux.git
- https://github.com/YogaRmdn/Linux_command

### alt + Prt Sc

<img width="3072" height="1670" alt="Screenshot From 2026-03-01 02-40-37" src="https://github.com/user-attachments/assets/4e433120-5cff-4bab-b424-f41fbc34c192" />


## Potong2 Video pkai CLI 
```swift
ffmpeg -i input.mp4 -ss 00:01:56 -to 00:02:29 ~/Downloads/output.mp4
ffmpeg -i Otakudesu_Ovlord.S2--11_720p.mp4 -ss 00:01:56 -to 00:02:29 ~/Downloads/shalltear-aa-rinn-suu.mp4
ffmpeg -i \[Kusonime\]\ Overlord\ S4\ BD\ -\ 05.mkv -ss 00:11:06 -to 00:12:27 ~/Downloads/maresaidarinse.mp4
```

## Timelapse Video
### to 30 seconds
```swift                                                                                                               
┌──(adminfid㉿kali)-[~/Downloads/test]
└─$ ffmpeg -i input.mp4 -vf "setpts=1/120*PTS,fps=60" -an output_smooth.mp4
                                                                                                                                                                                              
┌──(adminfid㉿kali)-[~/Downloads/test]
└─$ ffmpeg -i input.mp4 -vf "setpts=1/50*PTS" -an output_30s.mp4   
```

### make timelapse and add music in one command
```swift
ffmpeg -i input.mp4 -i music.mp3 -vf "setpts=1/120*PTS,fps=60" -c:a aac -map 0:v:0 -map 1:a:0 -shortest timelapsed-with-music.mp4
```

### add music to exsiting 30seconds video
```swift
ffmpeg -i exsiting.mp4 -i music.mp3 -c:v copy -c:a aac -map 0:v:0 -map 1:a:0 -shortest output_musik.mp4
```

### How to convert pdf to jpg in one directory
```bash
i=1; for f in *.pdf; do pdftoppm -jpeg -singlefile "$f" "$i"; ((i++)); done
```

Untuk mengecilkan ukuran gambar dari 8.2 MB menjadi sekitar 6 MB di Linux, cara paling cepat dan efisien adalah menggunakan terminal. Karena Anda memiliki target ukuran yang spesifik, ada dua alat berbasis teks (CLI) yang sangat direkomendasikan karena fitur pembatasan ukurannya.

Berikut adalah panduan langkah demi langkahnya:

### 1. Menggunakan ImageMagick (Paling Direkomendasikan)

ImageMagick adalah alat manipulasi gambar yang sangat kuat. Alat ini memiliki fitur luar biasa untuk file JPEG di mana Anda bisa langsung menetapkan target maksimal ukuran file, dan sistem akan menyesuaikan kompresinya secara otomatis.

**Langkah Instalasi:**
Buka terminal dan instal ImageMagick sesuai distribusi Linux Anda:

* **Ubuntu/Debian/Mint:** `sudo apt install imagemagick`
* **Fedora:** `sudo dnf install ImageMagick`
* **Arch Linux:** `sudo pacman -S imagemagick`

**Perintah Eksekusi:**
Gunakan perintah `convert` dengan opsi `-define jpeg:extent`.

```bash
convert gambar_asli.jpg -define jpeg:extent=6MB gambar_baru.jpg

```

> **Catatan:** Fitur `-define jpeg:extent` ini hanya bekerja secara efektif pada format file **.jpg** atau **.jpeg**. Perintah ini akan mencoba mempertahankan kualitas sebaik mungkin sambil memastikan hasil akhirnya tidak lebih dari 6 MB.

---

Cara paling mudah memperkecil ukuran file PDF di Linux melalui terminal adalah menggunakan Ghostscript. Jalankan perintah gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.5 -dPDFSETTINGS=/screen -dNOPAUSE -dBATCH -sOutputFile=hasil.pdf input.pdf di terminal Anda. [1, 2, 3] 
## Pilihan Pengaturan Kualitas (PDFSETTINGS)

* /screen: Resolusi 72 dpi, ukuran file paling kecil, cocok untuk web.
* /ebook: Resolusi 150 dpi, kualitas seimbang untuk baca.
* /printer: Resolusi 300 dpi, kualitas cetak. [1] 

## Langkah-langkah di Terminal

* Install ghostscript jika belum ada: sudo apt install ghostscript
* Masuk ke folder file PDF Anda.
* Ketik perintah kompresi dengan mengganti input.pdf dan hasil.pdf sesuai nama file Anda. [2, 4, 5] 

Jika Anda mau, saya bisa jelaskan cara kompres menggunakan tools GUI (tampilan grafis) atau metode lain seperti pdftoppm. Beritahu saya jika Anda membutuhkannya!

[1] [https://www.youtube.com](https://www.youtube.com/watch?v=nFFf3Q5acCg&t=103)
[2] [https://www.youtube.com](https://www.youtube.com/watch?v=efm_Dh9vSVU&t=5)
[3] [https://packages.fedoraproject.org](https://packages.fedoraproject.org/pkgs/shrinkpdf/shrinkpdf/fedora-41.html)
[4] [https://www.digitalocean.com](https://www.digitalocean.com/community/tutorials/reduce-pdf-file-size-in-linux)
[5] [https://community.claris.com](https://community.claris.com/en/s/question/0D53w0000680OtlCAE/best-recommendations-for-linux-server-doing-compression-on-pdf-files-it-creates)

___

Bisa, dan untuk kasus seperti ini saya menyarankan memakai `trafilatura`. Tool ini memang dirancang untuk mengekstrak konten utama halaman web, seperti judul, paragraf, heading, list, dan isi artikel, sambil membuang navbar, footer, menu, dan elemen web lain yang tidak relevan. Ia juga mendukung output Markdown, sehingga cukup nyaman untuk artikel tutorial yang berisi kode. ([Trafilatura][1])

Saya cek URL SantriKoding yang Anda berikan. Isi artikelnya memang tersedia di HTML dan bagian utamanya mencakup "Langkah 1 - Membuat Tema", "Langkah 2 - Konfigurasi Asset", "Langkah 3 - Konfigurasi Tema", serta kode Flutter/Dart. ([Santri Koding][2]) Jadi pendekatan ini cocok untuk halaman tersebut.

Untuk Kali/Debian/Ubuntu, pasang dulu:

```bash
sudo apt install pipx xclip
pipx ensurepath
pipx install trafilatura
```

Setelah itu, pola paling sederhana persis seperti `git diff | xclip` Anda:

```bash
trafilatura -u "https://santrikoding.com/tutorial-membuat-aplikasi-al-quran-dengan-flutter-3-konfigurasi-tema" \
  --markdown --no-comments \
  | xclip -selection clipboard
```

Sekarang tinggal paste ke ChatGPT dengan `Ctrl+V`.

Saya lebih menyarankan versi berikut karena URL sumber ikut masuk ke clipboard:

```bash
url="https://santrikoding.com/tutorial-membuat-aplikasi-al-quran-dengan-flutter-3-konfigurasi-tema"

{
    echo "SUMBER: $url"
    echo
    trafilatura -u "$url" --markdown --no-comments
} | xclip -selection clipboard
```

Hasil clipboard kira-kira akan berbentuk:

````text
SUMBER: https://santrikoding.com/...

# Tutorial Membuat Aplikasi Al-Quran Dengan Flutter #3: Konfigurasi Tema

### Langkah 1 - Membuat Tema

...

### Langkah 2 - Konfigurasi Asset

...

```yaml
flutter:
  assets:
    - assets/icons/
...
````

### Langkah 3 - Konfigurasi Tema

...

````

Ini lebih bagus daripada:

```bash
curl URL | pandoc ...
````

karena `trafilatura` melakukan main-content extraction, bukan sekadar mengubah seluruh HTML menjadi teks. Dokumentasinya memang menyediakan penggunaan langsung `trafilatura -u URL`, dan Markdown dapat dipilih dengan `--markdown`. ([Trafilatura][1])

Untuk artikel pemrograman, saya menyarankan jangan langsung memakai opsi `--precision`, sebab prioritas kita adalah jangan sampai bagian tutorial atau kode yang berguna terbuang. Kalau suatu website menghasilkan terlalu banyak sampah, barulah coba:

```bash
trafilatura -u "$url" \
  --markdown \
  --no-comments \
  --precision \
  | xclip -selection clipboard
```

`--precision` memang ditujukan untuk memprioritaskan ekstraksi bagian yang paling sentral dan mengurangi noise. ([Trafilatura][3])

Yang paling nyaman adalah membuat command sendiri, misalnya `webcopy`. Jika shell Anda Zsh, masukkan ini ke `~/.zshrc`:

```bash
webcopy() {
    local url="$1"

    if [[ -z "$url" ]]; then
        echo "Usage: webcopy <URL>"
        return 1
    fi

    {
        echo "SOURCE URL: $url"
        echo
        trafilatura -u "$url" \
            --markdown \
            --no-comments
    } | xclip -selection clipboard

    echo "✓ Konten artikel sudah disalin ke clipboard."
}
```

Reload:

```bash
source ~/.zshrc
```

Setelah itu Anda cukup melakukan:

```bash
webcopy https://santrikoding.com/tutorial-membuat-aplikasi-al-quran-dengan-flutter-3-konfigurasi-tema
```

Lalu:

```text
Ctrl+V
```

ke percakapan kita.

Untuk mengecek apa yang sudah masuk clipboard sebelum dikirim:

```bash
xclip -selection clipboard -o
```

atau hanya 50 baris pertama:

```bash
xclip -selection clipboard -o | head -n 50
```

Bisa juga cek ukurannya:

```bash
xclip -selection clipboard -o | wc -c
```

Saya bahkan menyarankan membuat versi `webcopy` yang otomatis menambahkan instruksi kepada saya. Contohnya:

```bash
webcopy() {
    local url="$1"

    if [[ -z "$url" ]]; then
        echo "Usage: webcopy <URL>"
        return 1
    fi

    {
        echo "Berikut adalah konten artikel yang saya ambil dari web."
        echo "Gunakan informasi ini sebagai referensi untuk membantu saya."
        echo
        echo "SOURCE URL: $url"
        echo
        echo "========== ARTICLE =========="
        trafilatura -u "$url" \
            --markdown \
            --no-comments
        echo
        echo "========== END ARTICLE =========="
    } | xclip -selection clipboard

    echo "✓ Artikel siap di-paste ke ChatGPT."
}
```

Dengan begitu workflow Anda menjadi sangat sederhana:

```bash
git diff | xclip -selection clipboard
```

untuk source code, dan:

```bash
webcopy https://example.com/artikel
```

untuk artikel web.

Satu catatan penting: ini mengekstrak **isi utama artikel**, bukan melakukan rangkuman secara semantik. Menurut saya itu justru paling tepat untuk dikirim kepada saya, karena kode, konfigurasi, argumentasi, dan langkah tutorial tetap utuh. Setelah Anda paste hasil `webcopy`, Anda bisa meminta saya seperti, "pelajari artikel ini dan sesuaikan dengan project saya", "ambil hanya langkah implementasinya", atau "bandingkan dengan kode saya sekarang".

[1]: https://trafilatura.readthedocs.io/en/latest/usage-cli.html?utm_source=chatgpt.com "Command-line usage — Trafilatura 2.2.0 documentation"
[2]: https://santrikoding.com/tutorial-membuat-aplikasi-al-quran-dengan-flutter-3-konfigurasi-tema "Tutorial Membuat Aplikasi Al-Quran Dengan Flutter #3: Konfigurasi Tema — SantriKoding.com — Website Belajar Coding Bahasa Indonesia Secara Terstruktur.
"
[3]: https://trafilatura.readthedocs.io/en/stable/usage-cli.html?utm_source=chatgpt.com "On the command-line — Trafilatura 2.2.0 documentation"
