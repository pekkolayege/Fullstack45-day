# Gün 07 · Asenkron JavaScript ve HTTP

[← Gün 6](../gun-06-dom-olaylar/README.md) · [Ana yol haritası](../README.md) · [Gün 8 →](../gun-08-typescript/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Asenkron JavaScript ve HTTP konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

fetch ağ isteği tamamlandığında yanıt nesnesi verir. HTTP 404 ve 500 yanıtları tek başına promise reddi değildir; response.ok kontrol edilmelidir. JSON ayrıştırma da hata verebilir. Örnek uygulamaya eklenecek fonksiyondur; /api/tasks uç noktası ayrıca gerekir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```javascript
async function loadTasks() {
  const response = await fetch('/api/tasks');
  // Başarısız HTTP yanıtını çağıranın yakalayacağı hataya dönüştürürüz.
  if (!response.ok) throw new Error(`HTTP ${response.status}`);
  return response.json();
}
// Çağrı yapan katman hatayı kullanıcıya uygun mesajla göstermelidir.
loadTasks().then(console.log).catch(error => console.error(error.message));
```

**Beklenen davranış:** Başarısız yanıt başarılı veri gibi işlenmez.

## Uygulama

200, 404 ve ağ kesintisi için beklediğin davranışı yaz; yerel sahte yanıtlarla dene.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Her hata CORS hatası değildir; önce ağ panelindeki durum kodunu incele.

## Kaynak

[Resmî dokümantasyon](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
