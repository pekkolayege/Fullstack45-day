# Gün 08 · TypeScript temel tipler

[← Gün 7](../gun-07-async-http/README.md) · [Ana yol haritası](../README.md) · [Gün 9 →](../gun-09-typescript-union/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

TypeScript temel tipler konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

TypeScript geliştirme sırasında tip uyumsuzluklarını yakalar; çalışma zamanındaki dış veriyi kendiliğinden doğrulamaz. type ile veri biçimi tanımlanabilir. Örneği TypeScript Playground içinde veya yapılandırılmış TypeScript projesinde dene.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```typescript
type Task = { id: number; title: string; completed: boolean };
// Dönüş tipi, fonksiyonun tüketicisine açık bir sözleşme sunar.
function pendingTitles(tasks: Task[]): string[] {
  return tasks.filter(task => !task.completed).map(task => task.title);
}
console.log(pendingTitles([{ id: 1, title: 'Tipleri öğren', completed: false }]));
```

**Beklenen davranış:** Geçersiz tip editörde işaretlenir; doğru veriyle başlık listesi döner.

## Uygulama

completed alanına metin vererek tip hatasını gözlemle; ardından düzelt.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

as kullanmak dış veriyi doğrulamaz; yalnızca derleyiciye iddiada bulunur.

## Kaynak

[Resmî dokümantasyon](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
