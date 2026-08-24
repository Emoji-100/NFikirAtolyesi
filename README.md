# NFikirAtölyesi

NFikirAtölyesi, NSosyal paylaşımlarını yapılandırılmış fikir kartlarına, açıklanabilir ekip eşleşmelerine ve uygulanabilir proje yol haritalarına dönüştürmek için geliştirilen sosyal yapay zekâ prototipidir.

## Çalışan ürün akışı

1. Kullanıcı fikrini doğal dille paylaşır ve açık rıza verir.
2. İçerik problem, çözüm, hedef kitle, etki alanı ve gereken yetkinlikler olarak yapılandırılır.
3. Benzer veya tamamlayıcı fikirler ile ekip adayları açıklanabilir gerekçelerle gösterilir.
4. Kullanıcının onayıyla proje odası ve düzenlenebilir ilk yol haritası oluşturulur.

## Veri şeffaflığı

- Başlangıçta gösterilen üç fikir açıkça `Demo senaryosu` olarak etiketlenir.
- Kullanıcı tarafından eklenen ve D1 üzerinde saklanan kayıtlar `Pilot kaydı` etiketi taşır.
- Kalıcı veri bağlantısı kullanılamadığında fikir yalnızca mevcut oturuma eklenir ve arayüz bunu açıkça bildirir.
- Takipçi sayısı eşleştirme puanında kullanılmaz.
- Canlı NSosyal entegrasyonu yapılmış gibi gösterilmez. Resmî API sözleşmesi sağlanana kadar uygulama izinli pilot verisi kullanır.

## Teknoloji

- Next.js 16, React 19 ve TypeScript
- Vinext ve Cloudflare Workers uyumlu sunucu çıktısı
- Cloudflare D1, Drizzle ORM ve şema göçleri
- Mobil uyumlu ve klavye ile erişilebilir arayüz
- NSosyal entegrasyonu için değiştirilebilir port ve adaptör katmanı

## Yerel çalıştırma

Node.js `22.13.0` veya daha yeni bir sürüm gereklidir.

```bash
npm ci
npm run dev
```

Üretim derlemesi ve kod denetimi:

```bash
npm run lint
npm run build
```

## Temel dizinler

- `app/`: ürün arayüzü ve fikir API rotası
- `db/`: D1 bağlantısı ve veri şeması
- `lib/ai/`: Türkçe fikir yapılandırma prototipi
- `lib/nsosyal/`: resmî entegrasyon için port ve adaptörler
- `docs/TECHNICAL_ARCHITECTURE.md`: üretim mimarisi, güvenlik ve entegrasyon sınırları

## NSosyal entegrasyon durumu

Prototip hiçbir özel uç nokta tahmin etmez ve izinsiz veri çekmez. Resmî taban adresi, OAuth kapsamları, veri sözleşmeleri ve webhook doğrulama yöntemi sağlandığında yalnızca `OfficialNSosyalAdapter` tamamlanarak canlı bağlantı açılabilir.
