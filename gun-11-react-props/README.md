# Gün 11 · Props ve bileşen tasarımı

[← Gün 10](../gun-10-react-baslangic/README.md) · [Ana yol haritası](../README.md) · [Gün 12 →](../gun-12-react-state/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Props ve bileşen tasarımı konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Props üst bileşenin alt bileşene verdiği verilerdir. Alt bileşen props'u doğrudan değiştirmez. Liste anahtarı öğenin sırası değil kalıcı kimliği olmalıdır. Örneği React projesinde bir bileşen dosyasında kullan.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```tsx
type Task = { id: number; title: string };
export function TaskList({ tasks }: { tasks: Task[] }) {
  return <ul>{tasks.map(task => (
    // Sabit kimlik React'in aynı öğeyi yeniden tanımasını sağlar.
    <li key={task.id}>{task.title}</li>
  ))}</ul>;
}
```

**Beklenen davranış:** Bileşenler veri almadan gizli global değişkene bağımlı değildir.

## Uygulama

TaskItem bileşeni çıkar. İki farklı veri listesiyle aynı TaskList bileşenini kullan.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Diziyi sıralarken index anahtarları yanlış öğe eşleşmesine yol açabilir.

## Kaynak

[Resmî dokümantasyon](https://react.dev/learn/passing-props-to-a-component)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
