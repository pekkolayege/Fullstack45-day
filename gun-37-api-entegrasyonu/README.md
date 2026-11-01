# Gün 37 · Frontend ve API entegrasyonu

[← Gün 36](../gun-36-yetkilendirme/README.md) · [Ana yol haritası](../README.md) · [Gün 38 →](../gun-38-hata-deneyimi/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Frontend ve API entegrasyonu konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Tipli istemci geliştirici hatalarını azaltır; gerçek sunucu yanıtını çalışma zamanında doğrulamak ayrıca gerekir. Örnek, önceden tanımlanmış oturum/CSRF ayarlı api istemcisini kullanır. Sunucunun data zarfı döndürdüğü varsayılır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```typescript
type Task = { id: number; title: string };
async function createTask(projectId: number, title: string): Promise<Task> {
  const response = await api.post(`/api/projects/${projectId}/tasks`, { title });
  const task = response.data?.data;
  // Sunucu sözleşmesi bozulursa sessizce yanlış state üretmeyiz.
  if (typeof task?.id !== 'number' || typeof task?.title !== 'string') {
    throw new Error('Beklenmeyen sunucu yanıtı');
  }
  return task;
}
```

**Beklenen davranış:** Başarılı kayıt yenilemeden sonra da veritabanından gelir.

## Uygulama

Formu gerçek API'ye bağla. Çift gönderimi engelle ve hata halinde kullanıcı girdisini koru.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Başarısız istekte başarılıymış gibi formu temizleme.

## Kaynak

[Resmî dokümantasyon](https://www.typescriptlang.org/docs/handbook/2/narrowing.html)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
