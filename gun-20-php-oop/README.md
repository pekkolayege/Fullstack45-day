# Gün 20 · PHP nesne yönelimli tasarım

[← Gün 19](../gun-19-php-http/README.md) · [Ana yol haritası](../README.md) · [Gün 21 →](../gun-21-composer/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

PHP nesne yönelimli tasarım konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Sınıf veriyle davranışı birlikte modelleyebilir. Kapsülleme iç durumun kontrolsüz değiştirilmesini sınırlar. Her şeyi sınıfa dönüştürmek yerine anlamlı kuralları bir yerde toplamak amaçlanır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
<?php
declare(strict_types=1);
final class Task {
    private bool $completed = false;
    public function __construct(public readonly string $title) {}
    public function complete(): void {
        // Dış kod durumu doğrudan değiştirmek yerine davranışı çağırır.
        $this->completed = true;
    }
    public function isCompleted(): bool { return $this->completed; }
}
$task = new Task('PHP öğren');
$task->complete();
var_dump($task->isCompleted());
```

**Beklenen davranış:** complete sonrası true, yeniden açma sonrası false döner.

## Uygulama

Yapıcıda boş başlığı reddet; yeniden açma davranışı ekle.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Sınıf içine HTTP, veritabanı ve görünüm sorumluluklarını birlikte yığma.

## Kaynak

[Resmî dokümantasyon](https://www.php.net/manual/en/language.oop5.php)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
