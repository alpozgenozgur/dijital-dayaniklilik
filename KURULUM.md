# Yönetim Paneli Kurulum Kılavuzu
### Dijital Dayanıklılık Projesi — web sitesi ve admin paneli

Bu site artık bir **yönetim paneline** sahip. Hoca (veya başka biri) `siteadi.netlify.app/admin` adresinden, **kod görmeden**, formlardan duyuru ve yazı ekleyebilir. Aşağıdaki adımlar bir kez yapılır; sonrasında içerik yönetimi tamamen panelden yürür.

> Not: Panel ve içerikler **yalnızca Netlify'da yayınlanmış** sitede çalışır. Dosyayı bilgisayarda açtığında ya da önizlemede Duyurular/Yazılar boş görünür — bu normaldir.

---

## Dosya yapısı
```
dijital-dayaniklilik-projesi/
├── index.html              → sitenin kendisi
├── netlify.toml            → "derleme yok" ayarı
├── admin/
│   ├── index.html          → yönetim paneli sayfası
│   └── config.yml          → panelin alanları (Türkçe)
├── _data/
│   ├── duyurular.json      → duyurular (panel buraya yazar)
│   └── yazilar.json        → yazılar (panel buraya yazar)
└── gorseller/              → panelden yüklenen görseller (otomatik oluşur)
```

---

## Adım 1 — GitHub'a yükle
1. GitHub'da yeni bir **repo** oluştur (ör. `dijital-dayaniklilik`). Public olması en kolayıdır.
2. Bu klasördeki **tüm dosyaları** repoya yükle (VS Code / GitHub Desktop / sürükle-bırak — sana kalmış).
3. Ana dalın adının **`main`** olduğundan emin ol (`admin/config.yml` içinde `branch: main` yazıyor; dalın adı farklıysa orayı düzelt).

## Adım 2 — Netlify'a bağla
1. Netlify → **Add new site → Import an existing project → GitHub** → az önceki repoyu seç.
2. Build ayarları: **Build command boş**, **Publish directory `.`** (zaten `netlify.toml` bunu söylüyor, dokunmana gerek yok). **Deploy.**
3. İstersen **Site configuration → Change site name** ile adresi düzelt.

## Adım 3 — Girişi (Identity) aç
1. Netlify panelinde **Site configuration → Identity → Enable Identity.**
2. **Identity → Registration** → **Invite only** seç (herkes kayıt olamasın, sadece davet ettiklerin).
3. **Identity → Services → Git Gateway → Enable Git Gateway.** (Panelin GitHub'a yazabilmesi için şart.)

## Adım 4 — Kullanıcı davet et
1. **Identity** sekmesi → **Invite users** → hocanın (ve gerekiyorsa kendinin) e-postasını gir.
2. Gelen e-postadaki bağlantıya tıklayıp **şifre** belirlenir. Artık `siteadi.netlify.app/admin` adresinden bu e-posta + şifreyle girilir.

---

## Panel nasıl kullanılır (hocaya anlatılacak kısım)
1. `siteadi.netlify.app/admin` adresine git, e-posta + şifreyle giriş yap.
2. Soldan **Duyurular** veya **Yazılar**'ı seç → **Duyuru Listesi**'ni aç.
3. Listenin altındaki **"Duyuru ekle"** ile yeni satır aç; **Başlık, Tarih, Etiket, Özet, İçerik** alanlarını doldur. Görsel gerekiyorsa İçerik editöründen yükle.
4. Sağ üstten **Publish → Publish now.** Birkaç dakikada sitede görünür.

Silme/düzenleme de aynı yerden: ilgili satırı aç, değiştir veya çöp kutusuyla sil, tekrar **Publish.**

---

## Sık karşılaşılanlar
- **/admin açılmıyor / boş:** `admin/config.yml` içindeki `branch` ile GitHub'daki dal adı aynı olmalı (`main`).
- **"Bir şey kaydedilemedi":** Git Gateway açık değildir (Adım 3.3).
- **Giriş ekranı çıkmıyor:** Identity kapalıdır (Adım 3.1).
- **Yeni içerik görünmüyor:** Netlify'da yeni "deploy" bitene kadar 1-2 dk bekle; tarayıcıyı yenile.

## İçerik dışı (sabit) sayfaları değiştirmek
Amaç, Kapsam, İş Paketleri, Ekip gibi sayfalar panelde değil, `index.html` içindedir; bunlar nadiren değişir. Değişmesi gerekirse `index.html` düzenlenip GitHub'a tekrar yüklenir (Netlify otomatik yayınlar).
