Also available in [English](index-en.md)

* [Android](#android)
* [Chrome, Edge, Brave, Opera](#chrome)
* [iOS & macOS](#apple)
* [Firefox, Pale Moon, Waterfox](#firefox)
* [Windows](#windows)
* [Warp Client](#warp)
* [Blokir iklan, tracker & malware](#hipokrit)
* [Efek samping](#pandora)
* [Yang tidak dilindungi](#outofscope)
* [Detail Teknis](#blabber)

<a name="android"></a>
## Android
### Pie (9) keatas
Buka `Settings` - `Network & internet` - `Advanced` - `Private DNS`. Tidak ada? Install [QuickShortcutMaker](https://play.google.com/store/apps/details?id=com.sika524.android.quickshortcut), masuk ke Settings, cari dan tap `com.android.settings. Settings$NetworkDashboardActivity`
 
Pilih `Private DNS provider hostname`
 
Coba salah satu :
 * `dns.google` [Google](https://developers.google.com/speed/public-dns/docs/dns-over-tls)
 * `security.cloudflare-dns.com` [Cloudflare](https://developers.cloudflare.com/1.1.1.1/1.1.1.1-for-families/setup-instructions/dns-over-https)
 * `dns.quad9.net` [Quad9](https://www.quad9.net/service/service-addresses-and-features#rec)
 * `dot.tiar.app` [Tiarap DNS](https://github.com/pengelana/blocklist#dot-dns-over-tls)
 * `doh.mullvad.net` [Mullvad](https://mullvad.net/en/help/dns-over-https-and-dns-over-tls/)
 
Save. Cek koneksi internet. Kalau tidak ada koneksi, coba lainnya. Kalau semua tidak bisa, pilih `Off`, buka [PortQuiz](http://portquiz.net:853) :
 * Kalau bisa dibuka, coba [provider lain](https://kb.adguard.com/en/general/dns-providers), pilih yang di baris `DNS-over-TLS`.
 * Kalau tidak bisa, ikuti panduan berikut

### Oreo (8) dan sebelumnya
Install [Nebulo](https://play.google.com/store/apps/details?id=com.frostnerd.smokescreen) atau [Intra](https://play.google.com/store/apps/details?id=app.intra), pilih salah satu provider bawaan. Kalau semua tidak bisa, coba [provider lain](https://github.com/curl/curl/wiki/DNS-over-HTTPS). Jika *masih* tidak bisa, ikuti panduan [Warp Client](#warp)
 
<a name="chrome"></a>
## Chrome, Edge, Brave, Opera
Buka `Settings`, cari dan aktifkan `Secure DNS` atau `DNS-over-HTTPS`, pilih salah satu provider bawaan. Kalau semua tidak bisa, pilih Custom dan masukkan [provider lain](https://github.com/curl/curl/wiki/DNS-over-HTTPS). Jika *masih* tidak bisa, ikuti panduan [Warp Client](#warp)
 
<a name="apple"></a>
## iOS & macOS
Import DoH dari salah satu [profile premade](https://dns.notjakob.com/premades.html), download dan buka filenya. Lalu ke `Settings` (iOS)/`System Preferences` (macOS), `Profile Downloaded`(iOS)/`Profie`(macOS), pilih install. Kalau semua tidak bisa, buat [custom profile](https://dns.notjakob.com/tool.html), pilih DoH dan masukkan [provider lain](https://github.com/curl/curl/wiki/DNS-over-HTTPS). Jika *masih* tidak bisa, ikuti panduan [Warp Client](#warp)

<a name="firefox"></a>
## Firefox, Pale Moon, Waterfox
Buka `Option`, cari `Network Settings`, aktifkan `Enable DNS over HTTPS`, pilih dari provider bawaan. Kalau semua tidak bisa, pilih Custom dan masukkan [provider lain](https://github.com/curl/curl/wiki/DNS-over-HTTPS). Jika *masih* tidak bisa, ikuti panduan [Warp Client](#warp)

<a name="windows"></a>
## Windows
Install [YogaDNS](https://yogadns.com/) untuk cover semua aplikasi di Windows, berguna kalau server game diblokir ISP. Tidak terlalu stabil, lebih ribet saat konfigurasi custom (DoH harus masukkan IP server, bukan cuma URL). Gunakan hanya jika memang butuh buka blokiran diluar browser.

<a name="warp"></a>
## Warp Client
Download dan install [Warp Client](https://developers.cloudflare.com/warp-client/warp-for-everyone/setting-up), untuk Linux bisa pakai [wcgf](https://github.com/ViRb3/wgcf). **Masih** belum bisa juga? Berarti perlu VPN (lain, karena technically Warp itu VPN). Kalau enggan pakai gratisan dari pihak ketiga yang nggak jelas atau butuh cepat, bisa [bikin sendiri di Oracle Cloud](https://medium.com/@devinjaystokes/how-to-setup-an-ad-blocking-wireguard-vpn-server-with-pihole-in-the-cloud-for-free-e814e45aac50) ([video link](https://github.com/chadgeary/cloudblock#cloud-deployments)), gratis, cuma modal kartu yang bisa verifikasi (Jenius, atau CC) dengan saldo ~300 ribu dikembalikan setelah verifikasi (ada dua tahap verifikasi), selamanya bisa traffic 5 TB sebulan dari total 10 TB (karena traffic VPN dihitung dua kali, antara client dan server, dan server dan situs tujuan) max speed 50 Mbps, bisa punya dua IP bersamaan di VPS berbeda (pengguna total bisa jauh lebih banyak tergantung traffic).

<a name="hipokrit"></a>
## Blokir iklan, tracker & malware
Setelah buka blokiran mau blokir yang nggak diinginkan? Bisa. Paling gampang pakai [AdGuard](https://kb.adguard.com/en/dns/setup-guide) (ada blokir iklan, iklan + bokep) atau [AhaDNS](https://ahadns.com/) (murni blokir iklan). Blokir lebih mendalam untuk materi dewasa bisa pakai [CleanBrowsing](https://cleanbrowsing.org/guides/). Kalau mereka diblokir ISP, bisa pakai provider [yang kurang terkenal](https://github.com/curl/curl/wiki/DNS-over-HTTPS). Kalau mau lebih mendetail, pilih sendiri filter iklannya, monitor anggota keluarga, filter untuk anak dll bisa pakai [NextDNS](https://nextdns.io/), tapi setelah lebih dari 300 ribu query dalam sebulan, filter & logging nggak jalan (semua request tembus) sampai bulan berikutnya kecuali langganan. Dan kalau ngerasa "oh bisa buat blokir bokep nih", ingat di atas itu semua panduannya juga bisa untuk ganti lagi ke provider yang nggak blokir, jadi nggak berguna untuk mencegah seseorang yang *sengaja* ingin buka. Blokir iklan juga tidak sebagus metode extension seperti uBlock Origin, gunanya lebih sebagai pelengkap untuk aplikasi/OS yang tidak bisa pasang ekstensi.

<a name="pandora"></a>
## Efek samping
Standar DoH bukan hanya bawa efek positif, ada beberapa efek negatif yang perlu diingat
### Filter jaringan lebih sulit
Jaringan bukan cuma seperti ISP yang "lah gua kan bayar ngapain lu sensor", tapi jaringan kantor, rumah dan sekolah jadi lebih sulit untuk diatur tanpa DPI, yang perangkatnya lebih mahal. DoT dan DoH juga mengabaikan konfigurasi di OS/jaringan. Misal, Chrome di Android diset memakai DoH A, query dari Chrome akan langsung dikirimkan ke DoH A, walaupun Private DNS diset ke DoT B, dan di jaringan menggunakan Do53 C.
### Virus dan iklan bisa tembus blokir
Yang bisa nembak DoH sendiri bukan cuma OS/browser, teorinya app apapun, bahkan situs, bisa bikin query ke server DoH mereka sendiri tanpa bisa dibaca oleh filter DNS.
### Lebih mudah untuk stalking
[NextDNS](https://nextdns.io/) dan [Cloudflare for Teams](https://www.cloudflare.com/teams/) memungkinkan stalker yang punya akses ke perangkat dalam 1 menit saja untuk ganti DoH yang digunakan ke endpoint DoH milik dia. Tanpa keluar uang dan menginstal apapun di perangkat korban, semua query DNS di perangkat itu bisa dipantau dari jaringan apapun.

<a name="outofscope"></a>
## Yang tidak dilindungi
Panduan disini hanya memungkinan *mengakses* situs yang diblokir, namun tidak *menyembunyikan* aktivitas tersebut dari ISP, pemerintah, universitas, sekolah atau kantor. Untuk aktivitas yang selama ini sering dilaporkan (dan ditangkap) melalui UU ITE, asumsikan bahwa orang BIN selalu membaca semua traffic. Kalau menggunakan jaringan/VPN/perangkat milik organisasi, asumsikan semua traffic dibaca oleh divisi IT dan dilaporkan ke atasan.

<a name="blabber"></a>
## Detail Teknis
Agar tersedia di internet, suatu situs harus dihost minimal di sebuah server yang memiliki/terjangkau dari public IP, berlaku seperti nomor telepon global. Umumnya, pemblokiran situs di Indonesia tidak memblokir langsung IP tersebut, hanya memodifikasi DNS query yang menanyakan IP dari domain (google.com, detik.com) suatu situs. Query DNS sangat mudah dimodifikasi oleh ISP karena standar DNS (Do53) tidak ada enkripsi, bahkan router murah pun bisa blokir/modifikasi query DNS.

Walau ada standar DNSCrypt sejak 2011 yang dienkripsi sehingga tidak bisa dibaca ataupun dimodifikasi ISP, adopsinya baik di provider maupun client masih terbatas sampai sekarang. Baru sejak standar DNS-over-TLS (DoT) dan DNS-over-HTTPS (DoH) diperkenalkan, berbagai provider maupun client mulai dari OS sampai browser mengadopsi, karena sebenarnya penerapannya sangat simple. DoT pakai port tersendiri (853), jadi sangat mudah untuk diblokir router/ISP, adopsi juga terbatas di Android. DoH lebih populer, didukung kedua browser utama (Chrome & Firefox, kebanyakan browser lain turunan dari mereka), iOS, macOS, dan (masih dalam Dev Channel) Windows. Penerapan DoH juga jauh lebih mudah: punya hosting PHP? Satu file pun cukup dengan [NotMikeDEV/DoH](https://github.com/NotMikeDEV/DoH). Punya akun Google Cloud? Tinggal copy paste dengan [tina-hello/doh-gcf](https://github.com/tina-hello/doh-gcf/tree/simpleDo53). Punya VPS? Ikuti instruksi sudah dapat fitur lengkap dengan [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome). Karena DoH berjalan diatas HTTPS, lebih sulit untuk router/ISP untuk membedakan dari traffic internet biasa.

Tapi sulit bukan berarti tidak mungkin. Traffic DoH punya kekhasan dari ukurannya yang sangat kecil, mudah untuk diblokir ISP yang memantau statistik traffic. Memakai DoT dan DoH juga tidak menyembunyikan domain maupun IP yang dikunjungi, karena traffic HTTPS pun masih mengekspos domain tujuan dengan SNI, dan ISP jelas masih melihat IP tujuan. Ada standar ECH yang bisa menyembunyikan SNI, tapi adopsi masih sangat terbatas. Untuk menghindari itu semua, bisa pakai VPN karena semua traffic tidak terlihat ISP. Warp pada dasarnya VPN yang hanya mengenkripsi sampai jaringan Cloudflare terdekat, dan menyertakan IP asli di header agar situs tujuan bisa memblokir pengguna tertentu tanpa memblokir semua pengguna Warp.

Untuk masalah privasi, menggunakan DNS selain dari ISP yang nggak blokir iklan/tracker (seperti AdGuard, NextDNS, AhaDNS) sebenarnya *mengurangi* privasi. Dalam koneksi normal cuma ISP dan situs tujuan yang tahu traffic, dengan custom DNS, provider DNS juga bisa membaca domain (misal mengunjungi `example.com/halaman`, yang bisa diketahui cuma `example.com`).
