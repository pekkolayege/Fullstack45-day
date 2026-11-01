# Gün 35 · Sanctum oturumu ve CSRF

[← Gün 34](../gun-34-kimlik-dogrulama/README.md) · [Ana yol haritası](../README.md) · [Gün 36 →](../gun-36-yetkilendirme/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Sanctum oturumu ve CSRF konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Birinci taraf SPA için Sanctum çerez tabanlı oturum kullanabilir. CSRF koruması, kimlik doğrulama ve CORS farklı sorunları çözer. Örnek aynı origin altında yapılandırılmış Laravel/Sanctum, /login uç noktası ve axios bağımlılığı varsayar. Ayrı alt alan adlarında Sanctum stateful alanları, credentials ve çerez ayarları ayrıca gerekir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```typescript
import axios from 'axios';
const api = axios.create({ withCredentials: true, withXSRFToken: true });
// Sunucu CSRF çerezini verdikten sonra istemci başlığı eşler.
await api.get('/sanctum/csrf-cookie');
// email ve password formdan alınan doğrulanmış değişkenlerdir.
await api.post('/login', { email, password });
const response = await api.get('/api/user');
console.log(response.data);
```

**Beklenen davranış:** Giriş sonrası kullanıcı bilgisi gelir; çıkış sonrası korumalı istek 401 döndürür.

## Uygulama

Resmî Sanctum SPA kurulumunu uygula. Giriş, korumalı istek ve çıkışı ayrı dene.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Oturum sorununu CSRF korumasını kapatarak çözme.

## Kaynak

[Resmî dokümantasyon](https://laravel.com/docs/13.x/sanctum)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
