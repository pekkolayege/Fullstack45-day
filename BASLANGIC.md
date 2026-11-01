# Başlamadan önce

[Ana yol haritası](README.md)

## Kullanım

Bu depoyu GitHub üzerinde okuyabilir veya indirebilirsin. Repo için sunucu başlatmak, npm install çalıştırmak ya da web sitesi kurmak gerekmez. Kod alıştırmalarını kendine ait ayrı klasör veya repoda yap.

## Ön koşullar

Temel HTML, CSS ve JavaScript bilgisi önerilir. İlk günler tekrar niteliğindedir. Bir kavram yeni geliyorsa kaynak bağlantısını inceleyip alıştırmayı tamamlamadan ilerleme.

## Aşamalara göre çalışma ortamı

| Günler | Gereken ortam |
| --- | --- |
| 01–07 | Git, editör, tarayıcı; isteğe bağlı Node.js |
| 08–09 | TypeScript Playground veya TypeScript çalışma alanı |
| 10–16 | Ayrı Vite React/TypeScript projesi ve uyumlu Node.js |
| 17–22 | PHP CLI; Gün 21 itibarıyla Composer |
| 23–26 | PostgreSQL alıştırma veritabanı; PDO örneği için pdo_pgsql |
| 27–39 | Ayrı Laravel projesi, Composer ve PostgreSQL |
| 40–45 | Önceki aşamaların projesi; test ve yayınlama araçları |

Laravel örnekleri 13.x belgeleriyle birlikte okunmalıdır. Kurulumda resmî dokümandaki PHP ve bağımlılık koşullarını doğrula. Vite için kullanılan şablonun Node.js koşullarını kontrol et. Uygulama projenin composer.lock ve package-lock.json dosyalarını kaydet; bu eğitim reposu bağımlılık kurulumu dağıtmaz.

## Kod parçalarını okuma

Her örneğin çalışma bağlamını önce oku. Controller metodu bir PHP sınıfı içine; JSX bir React çalışma alanına; SQL hazırlanmış alıştırma veritabanına aittir. Eksik sınıf, ilişki veya uç nokta belirtildiğinde bunları alıştırmanın parçası olarak oluştur. Metinlerde testlerin tamamı çalıştırılmış varsayımı yoktur.

JSON yorum satırı desteklemez. JSON örneklerinin açıklamaları çevresindeki metindedir; diğer dillerde kritik kararlar yorumlarla anlatılır.

## Çalışma döngüsü

30 dakika anlatım, 45 dakika örnek inceleme, 90 dakika uygulama ve 30 dakika kontrol/günlük ayırabilirsin. İlerlemek için yalnızca okumayı değil, günün davranışını göstermeyi hedefle.

**Hazırlayan:** Ege Pekkolay  
**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
