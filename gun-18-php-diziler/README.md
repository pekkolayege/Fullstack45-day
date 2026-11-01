# Gün 18 · PHP dizileri ve fonksiyonlar

[← Gün 17](../gun-17-php-temelleri/README.md) · [Ana yol haritası](../README.md) · [Gün 19 →](../gun-19-php-http/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

PHP dizileri ve fonksiyonlar konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

PHP dizileri sıralı anahtar-değer yapılarıdır. array_filter özgün anahtarları korur; JSON listesi isteniyorsa array_values ile yeniden indeksleme gerekebilir. Bu ayrım API yanıtlarının dizi yerine nesneye dönüşmesini önler.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
<?php
declare(strict_types=1);
$tasks = [
    ['id' => 1, 'completed' => true],
    ['id' => 2, 'completed' => false],
];
// JSON'da liste biçimini korumak için sayısal anahtarları yenileriz.
$pending = array_values(array_filter($tasks, fn(array $task): bool => !$task['completed']));
echo json_encode($pending, JSON_THROW_ON_ERROR);
```

**Beklenen davranış:** Çıktı köşeli parantezli listede yalnızca id:2 görevini içerir.

## Uygulama

Bekleyen görevleri başlıklarıyla döndüren fonksiyon ekle.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Filtrelenmiş dizinin anahtarlarının sıfırdan başladığını varsayma.

## Kaynak

[Resmî dokümantasyon](https://www.php.net/manual/en/function.array-filter.php)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
