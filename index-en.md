Juga tersedia dalam [Bahasa Indonesia](index.md)
* [Android](#android)
* [Chrome, Edge, Brave, Opera](#chrome)
* [iOS & macOS](#apple)
* [Firefox, Pale Moon, Waterfox](#firefox)
* [Windows](#windows)
* [Warp Client](#warp)
* [Block ad, tracker & malware](#hipokrit)
* [Side effect](#pandora)
* [Out of scope](#outofscope)
* [Technical detail](#blabber)

<a name="android"></a>
## Android
### Pie (9) and later
Go to `Settings` - `Network & internet` - `Advanced` - `Private DNS`. No such menu? Install [QuickShortcutMaker](https://play.google.com/store/apps/details?id=com.sika524.android.quickshortcut), open Settings, find and launch `com.android.settings.` `Settings` `$NetworkDashboardActivity`
 
Pick `Private DNS provider hostname`
 
Try one of :
 * `dns.google` [Google](https://developers.google.com/speed/public-dns/docs/dns-over-tls)
 * `security.cloudflare-dns.com` [Cloudflare](https://developers.cloudflare.com/1.1.1.1/1.1.1.1-for-families/setup-instructions/dns-over-https)
 * `dns.quad9.net` [Quad9](https://www.quad9.net/service/service-addresses-and-features#rec)
 * `dot.tiar.app` [Tiarap DNS](https://github.com/pengelana/blocklist#dot-dns-over-tls)
 * `doh.mullvad.net` [Mullvad](https://mullvad.net/en/help/dns-over-https-and-dns-over-tls/)
 
Save. Check your connection. If there's no connection, try the other item in the list. If none of them works, choose `Off`, open [PortQuiz](http://portquiz.net:853) :
 * If it load, try [other providers](https://kb.adguard.com/en/general/dns-providers), pick those in the `DNS-over-TLS` line.
 * If it doesn't load, try the following section

### Oreo (8) and previous
Install [Nebulo](https://play.google.com/store/apps/details?id=com.frostnerd.smokescreen) or [Intra](https://play.google.com/store/apps/details?id=app.intra), pick one of the built-in providers. If none of them works, try [other providers](https://github.com/curl/curl/wiki/DNS-over-HTTPS).
 
<a name="chrome"></a>
## Chrome, Edge, Brave, Opera
Open `Settings`, search and enable `Secure DNS` or `DNS-over-HTTPS`, pick one of the built-in providers. If none of them works, change to Custom and try [other providers](https://github.com/curl/curl/wiki/DNS-over-HTTPS). If *none* of them works, try [Warp Client](#warp) guide.
 
<a name="apple"></a>
## iOS & macOS
Import DoH from one of the [premade profiles](https://encrypted-dns.party/), download open the file. Then open `Settings` (iOS)/`System Preferences` (macOS), `Profile Downloaded`(iOS)/`Profie`(macOS), choose install. If none of them works, create a [custom profile](https://dns.notjakob.com/tool.html), pick DoH and enter [other providers](https://github.com/curl/curl/wiki/DNS-over-HTTPS). If *none* of them works, try [Warp Client](#warp) guide.

<a name="firefox"></a>
## Firefox, Pale Moon, Waterfox
Open `Settings`, search for `Secure DNS`, enable `Max Protection`, pick one of the built-in providers. If none of them works, change to Custom and try [other providers](https://github.com/curl/curl/wiki/DNS-over-HTTPS). If *none* of them works, try [Warp Client](#warp) guide.
<a name="windows"></a>
## Windows
Install [YogaDNS](https://yogadns.com/) to cover all applications running on Windows, useful if the game server is blocked by your ISP. Not too stable, harder to configure custom providers (DoH needs server IP, not just the URL). Use only if you need to unblock outside your browser.

In Windows 11 or Windows 10 Insider, open the Command Line as Administrator, type `netsh dns add encryption server=IP dohtemplate=DOH autoupgrade=yes udpfallback=no`, replace the IP and DOH with a [provider](https://github.com/curl/curl/wiki/DNS-over-HTTPS) that have both IP and DNS over HTTPS, then set the DNS through the UI to that IP.
<a name="warp"></a>
## Warp Client
Download and install [Warp Client](https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/download-warp), you can also use [wcgf](https://github.com/ViRb3/wgcf) and load the generated profile in [WireGuard](https://www.wireguard.com/install/). **Still** doesn't work? Then you'll need (other, since technically Warp is also) VPN. If you don't want to use shady free providers or need faster speed, [make your own on Oracle Cloud](https://medium.com/@devinjaystokes/how-to-setup-an-ad-blocking-wireguard-vpn-server-with-pihole-in-the-cloud-for-free-e814e45aac50) ([video link](https://github.com/chadgeary/cloudblock#cloud-deployments)), free, all you need is a card that can do online transaction (mostly credit cards) with about $20 available balance to be returned after verification (there will be two stages), 5 TB monthly traffics forever from total of 10 TB (since VPN traffic is counted twice, between client and server, then server and the site) max speed 50 Mbps, you can have two IP simultaneousy in different VPS (total users can be more depending on actual traffic).

<a name="hipokrit"></a>
## Block ad, tracker & malware
So you want to block stuff after unblocking them? Sure. Easiest to use [AdGuard](https://kb.adguard.com/en/dns/setup-guide) (there are adblocking, and adblocking+adult sites filtering) or [AhaDNS](https://ahadns.com/) (pure adblocking). For deeper blocks for adult content, use [CleanBrowsing](https://cleanbrowsing.org/guides/). If they are blocked by the ISP, use [less popular providers](https://github.com/curl/curl/wiki/DNS-over-HTTPS). For more details, custom ad filter, monitoring family member, child filter etc, use [NextDNS](https://nextdns.io/), but after 300 thousand queries in a month, filter & logging will be disabled (all requests will go through) until the next month unless you subscribe. And before you think "great, I can block porn", remember that all of the previous guide can also be used to switch back to non-blocking provider, so this is useless against someone who *wants* to open them. Adblocking is also less effective than extensions like uBlock Origin, this is meant for apps/OS where installing exxtension isn't possible.

<a name="pandora"></a>
## Side effect
The DoH standard didn't just brought positive effect, there are some negative effects you need to keep in mind
### Network filtering becomes harder
This isn't just for ISP where "wait, I'm paying for my connection, why should it get censored?", but also for office, home and school networks where filtering becomes harder without DPI, which require more expensive hardware. DoT and DoH also ignore OS/network settings. For example, if Chrome on Android is set to use DoH A, Chrome's queries will go straight to DoH A, even if Private DNS is set to DoT B, and the network use Do53 C.
### Virus dan ad can also go through the block
DoH itself isn't just available for OS/browser, in theory any apps, even sites, can create their own query to DoH server of their choosing without being read by DNS filter.
### Easier stalking
[NextDNS](https://nextdns.io/) and [Cloudflare for Teams](https://www.cloudflare.com/teams/) enable stalkers with direct access to the device to switch DoH provider under one minute to their own DoH endpoint. Without spending or installing anything in the victim's device, all DNS queries in that device can be monitored from anywhere.

<a name="outofscope"></a>
## Out of scope
This guide only enables *accessing* blocked sites, but doesn't *hide* the activities from the ISP, government, university, school or office. For activities that often reported (and prosecuted) under the ITE law (if you're a foreigner, in addition to the universally considered criminal activity, blasphemy, separatism, drug and even criticism can be ground for prosecution), assume that the local intelligence is reading all traffic. On organization's network/VPN/hardware, assume all traffic is read by the IT division and reported to their superior. 

<a name="blabber"></a>
## Technical Detail
To be accessible from the internet, a site must be hosted in a server that at least have/reachable from a public IP, which act like a global phone number. Usually, Indonesian ISP don't block the IP directly, but only modify DNS queries which ask the IP of a site domains (google.com, detik.com). DNS queries is very easy to modify by ISPs because the standard DNS (Do53) isn't encrypted, even cheap router can block or modify DNS queries.

Even though the encrypted DNSCrypt has existed since 2011 and can't be read or modified by ISP, the adoption by providers and clients are still limited until now. Only after
DNS-over-TLS (DoT) and DNS-over-HTTPS (DoH) is introduced, various providers and clients from OSes and browsers adopt them, because the actual implementation is very simple. DoT use its own port (853), so it's very easy to be blocked by router/ISP, and its adoption is also limited to Android. DoH is far more popular, supported by the two main browsers (Chrome & Firefox, most other browsers are derived from them), iOS, macOS, and (still in Dev Channel) Windows. DoH implementation is also much easier: One PHP file is enough with [NotMikeDEV/DoH](https://github.com/NotMikeDEV/DoH) or just a few minutes setting up Cloudflare Workers with [tina-hello/doh-cf-workers](https://github.com/tina-hello/doh-cf-workers). Got Google Cloud account? Just copy paste [tina-hello/doh-gcf](https://github.com/tina-hello/doh-gcf/tree/simpleDo53). Got VPS? Follow the instruction to get a feature complete [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome). Since DoH run on top HTTPS, it's harder for router/ISP to pick it up from regular internet traffic.

But harder doesn't mean impossible. DoH traffic have a signature from its very small packets, easier to block by ISP that collects traffic statistics. Using DoT and DoH also don't hide the visited domain or IP, since HTTPS traffic still expose the destionation domain with SNI, and the ISP obviously still know the destination IP. There is ECH standard which hide SNI, but the adoption is very limited. To avoid them all, VPN can be used because all traffic isn't readable by ISP. Warp is basically a VPN that only encrypt until the nearest Cloudflare network, and include the original IP in header so sites can block specific user without blocking all Warp user.

For privacy, using DNS other than ISP's, which doesn't block ad/tracker (such as AdGuard, NextDNS, AhaDNS) actually *reduce* privacy. In normal connection only the ISP and sites know about the traffic, while with custom DNS, the DNS provider can also read the domain (eg, on visiting `example.com/page`, they only see `example.com`).
