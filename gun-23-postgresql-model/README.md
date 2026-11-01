# Gün 23 · PostgreSQL ve veri modeli

[← Gün 22](../gun-22-php-dogrulama/README.md) · [Ana yol haritası](../README.md) · [Gün 24 →](../gun-24-sql-crud/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

PostgreSQL ve veri modeli konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Birincil anahtar kaydı, dış anahtar ilişkili kaydı belirtir. NOT NULL boş değerleri engeller; boş metni engellemez. PostgreSQL kurulu ayrı alıştırma veritabanında çalış. Örnek tabloları yalnızca bir kez oluştur.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```sql
-- Her projenin benzersiz ve otomatik üretilen kimliği vardır.
CREATE TABLE projects (
  id bigint GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
  name text NOT NULL CHECK (length(trim(name)) > 0)
);
CREATE TABLE tasks (
  id bigint GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
  project_id bigint NOT NULL REFERENCES projects(id),
  title text NOT NULL,
  completed boolean NOT NULL DEFAULT false
);
```

**Beklenen davranış:** Olmayan projeye bağlı kayıt dış anahtar kısıtıyla reddedilir.

## Uygulama

Önce proje, sonra görev ekle. Var olmayan proje kimliğiyle görev eklemeyi dene.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Uygulama doğrulaması veritabanı bütünlük kısıtlarının yerine geçmez.

## Kaynak

[Resmî dokümantasyon](https://www.postgresql.org/docs/current/tutorial.html)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
