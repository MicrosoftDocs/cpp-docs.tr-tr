---
description: 'Hakkında daha fazla bilgi edinin: &lt; hash_map&gt;'
title: '&lt;hash_map&gt;'
ms.date: 01/18/2018
f1_keywords:
- <hash_map>
helpviewer_keywords:
- hash_map header
ms.openlocfilehash: 9d8274958a0f6b89892ec2c1c70080cd090d1c03
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98125980"
---
# <a name="lthash_mapgt"></a>&lt;hash_map&gt;

> [!NOTE]
> Bu üst bilgi artık kullanılmıyor. Alternatif olarak [\<unordered_map>](unordered-map.md) .

Kapsayıcı sınıfı şablonları hash_map ve hash_multimap ve destekleyici şablonlarını tanımlar.

## <a name="syntax"></a>Syntax

```cpp
#include <hash_map>
```

### <a name="operators"></a>İşleçler

|Hash_map sürümü|Hash_multimap sürümü|Description|
|-----------------------|----------------------------|-----------------|
|[işleç! = (hash_map)](hash-map-operators.md#op_neq)|[işleç! = (hash_multimap)](hash-map-operators.md#op_neq_mm)|İşlecin sol tarafındaki hash_map veya hash_multimap nesnesinin sağ taraftaki hash_map veya hash_multimap nesnesine eşit olmadığını sınar.|
|[işleç = = (hash_map)](hash-map-operators.md#op_eq_eq)|[işleç = = (hash_multimap)](hash-map-operators.md#op_eq_eq_mm)|İşlecin sol tarafındaki hash_map veya hash_multimap nesnesinin sağ taraftaki hash_map veya hash_multimap nesnesine eşit olup olmadığını sınar.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Hash_map sürümü|Hash_multimap sürümü|Description|
|-----------------------|----------------------------|-----------------|
|[takas (hash_map)](hash-map-class.md#swap)|[takas (hash_multimap)](hash-multimap-class.md#swap)|İki hash_maps veya hash_multimaps öğelerini değiş tokuş eder.|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[hash_compare sınıfı](hash-compare-class.md)|Hash_map, hash_multimap, hash_set veya hash_multiset gibi karma ilişkilendirilebilir kapsayıcılardan herhangi biri tarafından kullanılabilecek bir nesneyi `Traits` , içerdikleri öğeleri sıralamak ve sağlaması için varsayılan bir parametre nesnesi olarak tanımlar.|
|[value_compare sınıfı](value-compare-class.md)|Hash_map öğelerini, hash_map göreli sıralarını belirleyerek kendi anahtar değerlerini karşılaştırarak karşılaştırabilen bir işlev nesnesi sağlar.|
|[hash_map Sınıfı](hash-map-class.md)|Her bir öğenin değeri benzersiz ve ilişkili bir veri değeri olan bir sıralama anahtarına sahip bir çiftin bulunduğu bir koleksiyondaki verilerin depolanması ve hızlı alımı için kullanılır.|
|[hash_multimap sınıfı](hash-multimap-class.md)|Her öğenin, değeri benzersiz olmayan bir sıralama anahtarına ve ilişkili bir veri değerine sahip olan bir çiftin bulunduğu bir koleksiyondaki verilerin depolanması ve hızlı alımı için kullanılır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<hash_map>

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](cpp-standard-library-reference.md)
