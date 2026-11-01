# Gün 24 · SQL CRUD ve parametreli sorgular

[← Gün 23](../gun-23-postgresql-model/README.md) · [Ana yol haritası](../README.md) · [Gün 25 →](../gun-25-sql-join/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

SQL CRUD ve parametreli sorgular konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

SQL ile kayıt oluşturur, okur, günceller ve sileriz. Kullanıcı girdisini sorguya metin birleştirmeyle eklemek SQL enjeksiyonuna neden olabilir. PDO örneği PostgreSQL sürücüsü ve önceden oluşturulmuş $pdo bağlantısı gerektirir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
<?php
// Sorgu yapısı ile veri ayrı gönderilir; tırnakları elle kaçırmayız.
$statement = $pdo->prepare('SELECT id, title FROM tasks WHERE project_id = :project_id');
$statement->execute(['project_id' => 1]);
$tasks = $statement->fetchAll(PDO::FETCH_ASSOC);
print_r($tasks);
```

**Beklenen davranış:** Başlık bozulmadan saklanır; UPDATE yalnızca hedef kaydı değiştirir.

## Uygulama

Parametreli INSERT ve UPDATE ekle; tek tırnak içeren bir görev başlığıyla dene.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

WHERE olmadan UPDATE veya DELETE tüm tabloyu etkileyebilir; alıştırma veritabanı kullan.

## Kaynak

[Resmî dokümantasyon](https://www.php.net/manual/en/pdo.prepared-statements.php)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
