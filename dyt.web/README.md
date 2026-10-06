 ## Diyetisyen Web Sitesi

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![WhatsApp](https://img.shields.io/badge/WhatsApp-randevu-25D366?logo=whatsapp&logoColor=white)
![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-uyumlu-2ea44f?logo=github&logoColor=white)

Ziyaretçilerin form doldurarak **WhatsApp üzerinden randevu talep edebildiği**, Türkçe ve mobil uyumlu bir kişisel web sitesi. Framework, paket yöneticisi veya sunucu gerektirmez; yalnızca HTML, CSS ve JavaScript ile yazılmıştır.

## Canlı Demo

🌐 **[Siteyi görüntüle](https://egerzz.github.io/diyetisyen-web/)**

<!-- Ekran görüntüsü eklemek için dosyayı docs/ klasörüne koyup aşağıdaki satırı etkinleştirin:
![Ana sayfa](docs/screenshot.png)
-->

## İçindekiler

- [Özellikler](#özellikler)
- [Sayfa bölümleri](#sayfa-bölümleri)
- [Kullanılan teknolojiler](#kullanılan-teknolojiler)
- [Proje yapısı](#proje-yapısı)
- [Kurulum ve çalıştırma](#kurulum-ve-çalıştırma)
- [WhatsApp randevu formunu ayarlama](#whatsapp-randevu-formunu-ayarlama)
- [Özelleştirme](#özelleştirme)
- [GitHub Pages ile yayınlama](#github-pages-ile-yayınlama)
- [Yayından önce yapılacaklar](#yayından-önce-yapılacaklar)
- [Lisans](#lisans)

## Özellikler

- **WhatsApp ile randevu:** Ad soyad, telefon, görüşme türü, görüşme şekli (yüz yüze / online), tarih, saat ve not alanları; form gönderilince bilgiler hazır bir mesaj olarak WhatsApp'ta açılır.
- **Akıllı tarih seçimi:** Geçmiş tarihler seçilemez.
- **Açık / koyu tema:** Üst menüdeki ampul simgesiyle tek tıkla tema değişimi.
- **Mobil uyumlu tasarım:** Telefon, tablet ve masaüstü ekranlara uyum sağlayan duyarlı düzen ve açılır mobil menü.
- **Akıcı gezinme:** Menü bağlantılarında yumuşak kaydırma (smooth scroll) ve sabit üst menü.
- **Blog bölümü:** Hover efektli, kart yapısında yazı listesi.
- **Hakkında bölümü:** Tanıtım metni ve deneyim, danışan sayısı, memnuniyet gibi istatistik kartları.
- **Hafif yapı:** Derleme adımı yok, tarayıcıda doğrudan çalışır.

## Sayfa bölümleri

| Bölüm | Bağlantı | İçerik |
|---|---|---|
| Ana sayfa | `#home` | Karşılama alanı, kısa tanıtım ve "randevu al" düğmesi |
| Hakkımızda | `#about` | Diyetisyen tanıtımı ve istatistikler |
| Randevu | `#booking` | WhatsApp'a yönlendiren randevu formu |
| Blog | `#blogs` | Beslenme üzerine yazı kartları |

> **Paketler** (`#prices`) bölümü menüde yer alıyor ancak henüz eklenmedi. Ayrıntı için [Yayından önce yapılacaklar](#yayından-önce-yapılacaklar) başlığına bakın.

## Kullanılan teknolojiler

- **HTML5:** Anlamsal bölümler (`header`, `section`, `article`, `nav`, `form`)
- **CSS3:** Özel değişkenler (CSS variables), Flexbox, Grid, `clamp()` ile akışkan başlıklar, medya sorguları
- **JavaScript (ES6):** Randevu formu ve WhatsApp mesajı oluşturma, tarih sınırlaması
- **[Google Fonts](https://fonts.google.com/):** DM Sans, Playfair Display, Playwrite CU Guides
- **[Font Awesome](https://fontawesome.com/):** Menü, tema ve blog bağlantı simgeleri

## Proje yapısı

```text
dyt-dila-ozdemir/
├── img/
│   ├── bg.jpg          # Ana sayfa arka planı
│   ├── about.jpg       # Hakkımda bölümü görseli
│   ├── blog1.jpg       # Blog görselleri
│   ├── blog2.jpg
│   ├── blog3.jpg
│   └── logo.jpg        # Logo
├── index.html          # Sayfa içeriği ve randevu formu betiği
├── style.css           # Tasarım ve duyarlı düzen
└── README.md
```

## Kurulum ve çalıştırma

Depoyu bilgisayarınıza indirin:

```bash
git clone https://github.com/<kullanici-adi>/<depo-adi>.git
cd <depo-adi>
```

Ardından `index.html` dosyasına çift tıklayarak tarayıcıda açın. Ek bir kurulum gerekmez.

İsterseniz yerel sunucu ile de çalıştırabilirsiniz (Python kuruluysa):

```bash
python -m http.server 8000
```

Tarayıcıda `http://localhost:8000` adresini açın.

> Yazı tipleri Google Fonts üzerinden yüklendiği için tam görünüm için internet bağlantısı gerekir.

## WhatsApp randevu formunu ayarlama

Randevu formu, `index.html` dosyasının sonundaki `<script>` bölümünde çalışır. Mesajların kendi numaranıza gelmesi için aşağıdaki satırı düzenleyin:

```js
// Başında 0 ve + olmadan, 90 ile başlayarak yazın
const phoneNumber = '905XXXXXXXXX';
```

Örnek: `0532 123 45 67` numarası için `905321234567`.

Form gönderildiğinde `https://wa.me/<numara>?text=...` adresi yeni sekmede açılır ve randevu bilgileri hazır bir mesaj olarak gelir. Gönderme işlemini ziyaretçi WhatsApp içinde onaylar; bu nedenle sunucu veya veri tabanı gerekmez.

## Özelleştirme

- **Renkler:** `style.css` dosyasının başındaki `:root` bölümünde bulunan `--main-color` değişkenini değiştirerek ana rengi güncelleyebilirsiniz. Koyu tema renkleri `body:has(#themeToggler:checked)` bloğunda tanımlıdır.
- **Yazı tipleri:** Logo için Playwrite CU Guides, başlıklar için Playfair Display, gövde metni için DM Sans kullanılır.
- **Görüşme türleri ve saatler:** `index.html` içindeki randevu formunda `<select>` listelerine seçenek ekleyebilir veya çıkarabilirsiniz.
- **Blog yazıları:** `#blogs` bölümündeki `<article class="post">` bloğunu kopyalayarak yeni yazı kartı ekleyin; görseli `img/` klasörüne koyun.
- **Görseller:** Aynı adla `img/` klasörüne yeni dosya koyarak görselleri değiştirebilirsiniz.

## GitHub Pages ile yayınlama

1. Projeyi GitHub deposuna yükleyin (`index.html` ana klasörde olmalı).
2. Depoda **Settings → Pages** bölümünü açın.
3. **Build and deployment** altında kaynak olarak **Deploy from a branch** seçin.
4. Dal olarak `main`, klasör olarak `/ (root)` seçip **Save** düğmesine basın.
5. Birkaç dakika içinde site `https://<kullanici-adi>.github.io/<depo-adi>/` adresinde yayına girer.

## Yayından önce yapılacaklar

- [ ] `index.html` içinde `phoneNumber` değerini gerçek WhatsApp numarasıyla değiştirin (`905XXXXXXXXX` yer tutucudur).
- [ ] **Paketler** (`#prices`) bölümünü ekleyin ya da menüdeki "paketler" bağlantısını kaldırın.
- [ ] Simgelerin görünmesi için `<head>` içine Font Awesome bağlantısını ekleyin.
- [ ] `<head>` içine `<title>` ve `<meta name="description">` etiketlerini ekleyin (sekme başlığı ve arama sonuçları için).
- [ ] İstatistik kartlarındaki değerleri (yıl deneyim, danışan sayısı, memnuniyet) gerçek bilgilerle güncelleyin.
- [ ] Blog yazılarındaki "devamını oku" bağlantılarını (`href="#"`) gerçek yazı sayfalarına yönlendirin.
- [ ] Menüdeki kullanıcı ve kalp simgelerini bir işleve bağlayın ya da kaldırın.
- [ ] Menü düğmesi için tekrar eden `id="menu-btn"` kullanımını düzeltin (her `id` sayfada yalnızca bir kez kullanılmalıdır).
- [ ] `docs/screenshot.png` ekran görüntüsünü ekleyip README'deki satırı etkinleştirin.

## Lisans

Lisans henüz belirtilmemiştir. Açık kaynak olarak paylaşmayı düşünüyorsanız depoya bir `LICENSE` dosyası ekleyin (örneğin MIT).

---

Sitedeki beslenme içerikleri genel bilgilendirme amaçlıdır ve kişiye özel tıbbi tavsiye yerine geçmez.
