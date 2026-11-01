# Gün 13 · React formları

[← Gün 12](../gun-12-react-state/README.md) · [Ana yol haritası](../README.md) · [Gün 14 →](../gun-14-yonlendirme/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

React formları konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Kontrollü form alanının değeri state'ten gelir ve onChange ile güncellenir. Gönderim sırasında kullanıcı girdisi normalize edilir. İstemci doğrulaması kullanıcı deneyimini iyileştirir; sunucudaki doğrulama ayrıca gereklidir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```tsx
import { useState, type FormEvent } from 'react';
export function TaskForm() {
  const [title, setTitle] = useState('');
  const [error, setError] = useState('');
  function submit(event: FormEvent<HTMLFormElement>) {
    event.preventDefault();
    // Yalnızca boşluk içeren metin de boş kabul edilir.
    setError(title.trim() ? '' : 'Başlık zorunludur.');
  }
  return <form onSubmit={submit}>
    <label>Başlık<input value={title} onChange={e => setTitle(e.target.value)} /></label>
    <button type="submit">Kontrol et</button><p role="alert">{error}</p>
  </form>;
}
```

**Beklenen davranış:** Boşluklardan oluşan giriş hata verir; Enter ile gönderim çalışır.

## Uygulama

120 karakter sınırı ve başarılı gönderimde alan temizleme ekle.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Kontrollü alanın ilk değerini undefined yerine boş metin olarak başlat.

## Kaynak

[Resmî dokümantasyon](https://react.dev/reference/react-dom/components/input)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
