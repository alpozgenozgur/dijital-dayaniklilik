# Dijital Dayanıklılık Projesi — Tanıtım ve Yaygınlaştırma Sitesi

Sınıf öğretmenlerinin **dijital dayanıklılık** ve dijital dayanıklılık özyeterliklerini güçlendirmeye yönelik TÜBİTAK 1001 araştırma projesinin (Amasya Üniversitesi) resmî tanıtım ve yaygınlaştırma web sitesi.

🔗 **Canlı site:** https://dijitaldayaniklilik.netlify.app
🛠️ **Yönetim paneli:** `…/admin` (Netlify Identity ile korumalı)

---

## Proje hakkında

Site, projenin amacını, kuramsal çerçevesini (NIST tabanlı **ANKA modeli**), iş paketlerini, ekibini ve çıktılarını kamuya açık biçimde sunar. Ayrıca **kod bilgisi gerektirmeyen** bir içerik yönetim paneli içerir: duyurular, yazılar, etkinlikler, yayınlar ve ekip bilgileri panelden güncellenir.

## Öne çıkan özellikler

- **Tek dosya, derleme gerektirmeyen** (build-less) statik site — hızlı ve bakımı kolay.
- **Çok sayfalı gezinme** (JS tabanlı yönlendirme) — uzun kaydırma yerine sade sayfalar.
- **Decap CMS yönetim paneli** — Netlify Identity + Git Gateway ile güvenli giriş; içerik `_data/*.json` dosyalarında tutulur.
- **Duyarlı (responsive)** ve erişilebilir tasarım; özel tipografi ve renk paleti.
- İçerik İngilizceye genişletilebilir altyapıyla hazırlandı (TR/EN anahtarı).

## Kullanılan teknolojiler

`HTML5` · `CSS3` · `Vanilla JavaScript` · `Decap CMS` · `Netlify (Identity, Git Gateway)` · `Markdown/JSON içerik`

## Proje yapısı

```
├── index.html          → Site (tasarım + sayfalar + içerik yükleme)
├── netlify.toml        → Netlify yapılandırması (derleme yok)
├── admin/
│   ├── index.html      → Decap CMS panel sayfası
│   └── config.yml      → Panel bölümleri ve alanları
└── _data/              → Panelin yazdığı içerik dosyaları
    ├── site.json       → Genel ayarlar (şu anki aşama, iletişim)
    ├── ekip.json       → Ekip üyeleri
    ├── etkinlikler.json→ Süreç ve etkinlikler
    ├── yayinlar.json   → Yayınlar ve çıktılar
    ├── duyurular.json  → Duyurular
    └── yazilar.json    → Bilgilendirme yazıları
```

## İçerik yönetimi

İçerik, `…/admin` adresindeki panelden form arayüzüyle düzenlenir; kaydedildiğinde GitHub deposuna işlenir ve Netlify siteyi otomatik yeniden yayınlar. Kurulum ve kullanım ayrıntıları için [`KURULUM.md`](KURULUM.md) dosyasına bakınız.

## Lisans / Kullanım

Bu depo, TÜBİTAK 1001 projesi (Amasya Üniversitesi) kapsamında geliştirilen tanıtım sitesinin kaynak kodudur.

---

*Geliştirme: Özgür Alpözgen — CEIT, ODTÜ.*
