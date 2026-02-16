# Güvenlik Kontrol Listesi (Frontend Odaklı)

Bu proje statik bir landing page olduğundan ve bir backend veya veritabanı entegrasyonu içermediğinden, geleneksel backend güvenlik zafiyetleri (SQL Injection, CSRF, vb.) doğrudan geçerli değildir. Ancak frontend tarafında da dikkat edilmesi gereken bazı noktalar bulunmaktadır.

## Genel Frontend Güvenliği

- [x] **XSS (Cross-Site Scripting) Koruması (Minimal):** Kullanıcıdan doğrudan veri alınıp DOM'a basılan bir alan bulunmasa da, ileride eklenebilecek dinamik içerikler için güvenli kodlama pratikleri (escape input) gözetilmelidir.
- [x] **Tırd Partı Kütüphane Güvenliği:** Kullanılan JavaScript kütüphanelerinin (e.g., TailwindCSS, herhangi bir future JS lib) bilinen güvenlik açıkları için düzenli kontrolü.
- [ ] **Content Security Policy (CSP):** `<meta http-equiv="Content-Security-Policy" ...>` etiketi ile kaynak kısıtlamaları uygulanabilir. (Şu an için gerekli değil, ancak ileride ek kaynaklar entegre edilirse düşünülebilir.)
- [ ] **SSL/TLS Kullanımı:** Web sitesinin HTTPS üzerinden sunulduğundan emin olun. (Deployment aşamasında web sunucusu/CDN tarafından sağlanacaktır.)
- [ ] **Clickjacking Koruması:** `X-Frame-Options` HTTP başlığı ile sayfanın iframe içinde gösterilmesi engellendi mi? (Statik sayfa için genelde sorun değil, ancak hassas içerik barındıran sayfalarda önemlidir. Deployment'ta sunucu ayarı yapılabilir.)
- [ ] **Güvenlik Başlıkları:** HTTP Strict Transport Security (HSTS), X-Content-Type-Options gibi güvenlik başlıkları deployment ortamında yapılandırıldı mı?

## Backend/Veritabanı İlişkili Güvenlik (N/A)

Bu proje bir backend veya veritabanı içermediği için aşağıdaki maddeler geçerli değildir:

- [N/A] JWT (JSON Web Tokens) güvenliği
- [N/A] CORS (Cross-Origin Resource Sharing) yapılandırması
- [N/A] SQL injection koruması
- [N/A] CSRF (Cross-Site Request Forgery) koruması
- [N/A] Kimlik doğrulama ve yetkilendirme mekanizmaları
- [N/A] API Rate Limiting
- [N/A] Hassas verilerin şifrelenmesi (aktarımda ve saklamada)
- [N/A] Dosya yükleme güvenlik kontrolleri
- [N/A] Loglama ve İzleme mekanizmaları