* [Android](#android)
* [Chrome, Edge, Brave, Opera](#chrome)
* [iOS & macOS](#apple)
* [Firefox, Pale Moon, Waterfox](#firefox)
* [Warp Client](#warp)

<a name="android"></a>
## Android
### Pie (9) keatas
 Buka `Settings` - `Network & internet` - `Advanced` - `Private DNS`. Tidak ada? Install [QuickShortcutMaker](https://play.google.com/store/apps/details?id=com.sika524.android.quickshortcut), masuk ke Settings, cari dan tap `com.android.settings.Settings$NetworkDashboardActivity`
 
 Pilih `Private DNS provider hostname`
 
 Coba salah satu :
 * `dns.google`
 * `one.one.one.one`
 * `dns.quad9.net`
 * `public.dns.iij.jp`
 * `doh.mullvad.net`
 
 Save. Cek koneksi internet. Kalau tidak ada koneksi, coba lainnya. Kalau semua tidak bisa, pilih `Off`, buka http://portquiz.net:853 :
 * Kalau bisa dibuka, cari dari https://kb.adguard.com/en/general/dns-providers, pilih yang di baris `DNS-over-TLS`.
 * Kalau tidak bisa, ikuti panduan berikut

### Oreo (8) dan sebelumnya
 Install [Nebulo](https://play.google.com/store/apps/details?id=com.frostnerd.smokescreen) atau [Intra](https://play.google.com/store/apps/details?id=app.intra), pilih salah satu provider bawaan. Kalau semua tidak bisa, coba provider lain dari https://github.com/curl/curl/wiki/DNS-over-HTTPS. Jika *masih* tidak bisa, ikuti panduan [Warp Client](#warp)
 
 <a name="chrome"></a>
 ## Chrome, Edge, Brave, Opera
 Buka `Settings`, cari dan aktifkan `Secure DNS` atau `DNS-over-HTTPS`, pilih salah satu provider bawaan. Kalau semua tidak bisa, pilih Custom dan masukkan provider lain dari https://github.com/curl/curl/wiki/DNS-over-HTTPS. Jika *masih* tidak bisa, ikuti panduan [Warp Client](#warp)
 
 <a name="apple"></a>
 ## iOS & macOS
 Import DoH dari salah satu profile di https://dns.notjakob.com/premades.html, download dan buka filenya. Lalu ke `Settings` (iOS)/`Sytem Preferences` (macOS), `Profile Downloaded`(iOS)/`Profie`(macOS), pilih install. Kalau semua tidak bisa, pilih buat custom profile dengan https://dns.notjakob.com/tool.html, pilih DoH dan masukkan provider dari https://github.com/curl/curl/wiki/DNS-over-HTTPS. Jika *masih* tidak bisa, ikuti panduan [Warp Client](#warp)

<a name="firefox"></a>
## Firefox, Pale Moon, Waterfox
Buka `Option`, cari `Network Settings`, aktifkan `Enable DNS over HTTPS`, pilih dari provider bawaan. Kalau semua tidak bisa, pilih Custom dan masukkan provider lain dari https://github.com/curl/curl/wiki/DNS-over-HTTPS. Jika *masih* tidak bisa, ikuti panduan [Warp Client](#warp)

<a name="warp"></a>
## Warp Client
Download dan install [Warp Client](https://developers.cloudflare.com/warp-client/warp-for-everyone/setting-up), untuk Linux bisa pakai [wcgf](https://github.com/ViRb3/wgcf). **Masih** belum bisa juga? Berarti perlu VPN (lain, karena technically Warp itu VPN). Kalau enggan pakai gratisan dari pihak ketiga yang nggak jelas atau butuh cepat, bisa [bikin sendiri di Oracle Cloud](https://medium.com/@devinjaystokes/how-to-setup-an-ad-blocking-wireguard-vpn-server-with-pihole-in-the-cloud-for-free-e814e45aac50) ([video link](https://github.com/chadgeary/cloudblock#cloud-deployments), gratis, cuma modal kartu yang bisa verifikasi (Jenius, atau CC) dengan saldo ~300 ribu (dikembalikan setelah verifikasi, ada dua tahap verifikasi), selamanya bisa traffic 5 TB sebulan (dari total 10 TB, karena traffic VPN dihitung dua kali) max 50 Mbps.
