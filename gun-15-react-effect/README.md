# Gün 15 · Effect ve istek yaşam döngüsü

[← Gün 14](../gun-14-yonlendirme/README.md) · [Ana yol haritası](../README.md) · [Gün 16 →](../gun-16-frontend-kontrol/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Effect ve istek yaşam döngüsü konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Effect dış sistemle eşitleme içindir. İstek sürerken bileşen kaldırılabilir veya yeni istek başlayabilir. İptal sinyali eski isteğin gereksiz çalışmasını önler. Örnek React bileşenindeki useEffect gövdesine uyarlanacak parçadır; setError ve setTasks state güncelleyicileri önceden tanımlı olmalıdır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```tsx
useEffect(() => {
  const controller = new AbortController();
  fetch('/api/tasks', { signal: controller.signal })
    .then(response => {
      if (!response.ok) throw new Error('Görevler yüklenemedi');
      return response.json();
    })
    .then(setTasks)
    .catch(error => {
      // Kullanıcının ekran değiştirmesi hata mesajı olarak gösterilmez.
      if (error.name !== 'AbortError') setError(error.message);
    });
  return () => controller.abort();
}, []);
```

**Beklenen davranış:** İptal edilen istek kullanıcıya hata olarak gösterilmez.

## Uygulama

Yükleniyor, boş ve hata görünümlerini ekle. Ekrandan ayrılırken isteği iptal et.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Bağımlılık listesini susturmak yerine effect'in hangi verilere bağlı olduğunu çöz.

## Kaynak

[Resmî dokümantasyon](https://react.dev/reference/react/useEffect)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
