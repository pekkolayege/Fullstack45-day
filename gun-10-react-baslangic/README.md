# Gün 10 · React ve bileşenler

[← Gün 9](../gun-09-typescript-union/README.md) · [Ana yol haritası](../README.md) · [Gün 11 →](../gun-11-react-props/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

React ve bileşenler konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

React arayüzü bileşenlerden oluşturur. JSX JavaScript içinde arayüz tanımıdır. Bileşen adları büyük harfle başlar. Vite React/TypeScript çalışma alanı kurduktan sonra aşağıdaki örneği src/App.tsx içine yerleştir; bu repo hazır bir web uygulaması dağıtmaz.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```tsx
// Varsayılan dışa aktarım başlangıç dosyasının bileşeni yüklemesini sağlar.
export default function App() {
  return <main><h1>Görevlerim</h1><p>İlk React bileşenim.</p></main>;
}
```

**Beklenen davranış:** Geliştirme ekranında başlık görünür; npm run build başarılıdır.

## Uygulama

Resmî Vite rehberindeki react-ts şablonunu ayrı çalışma alanında kur. App bileşenini değiştir ve derle.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

JSX içinde class yerine className kullanılır.

## Kaynak

[Resmî dokümantasyon](https://vite.dev/guide/)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
