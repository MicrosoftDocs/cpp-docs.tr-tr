---
title: '&lt;hash_map &gt;'
ms.date: 01/18/2018
f1_keywords:
- <hash_map>
- std::<hash_map>
helpviewer_keywords:
- hash_map header
ms.openlocfilehash: e586a933c2a80b7e611bcd4b4714e300eb21a0ad
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689568"
---
# <a name="lthash_mapgt"></a>&lt;hash_map &gt;

> [!NOTE]
> Bu üst bilgi artık kullanılmıyor. Alternatif, [\<unordered_map >](unordered-map.md).

Hash_map ve hash_multimap kapsayıcı sınıfı şablonlarını ve bunların destekleyici şablonlarını tanımlar.

## <a name="syntax"></a>Sözdizimi

```
#include <hash_map>
```

### <a name="operators"></a>İşleçler

|Hash_map sürümü|Hash_multimap sürümü|Açıklama|
|-----------------------|----------------------------|-----------------|
|[işleç! = (hash_map)](hash-map-operators.md#op_neq)|[işleç! = (hash_multimap)](hash-map-operators.md#op_neq_mm)|İşlecin sol tarafındaki hash_map veya hash_multimap nesnesinin sağ taraftaki hash_map veya hash_multimap nesnesine eşit olup olmadığını sınar.|
|[operator = = (hash_map)](hash-map-operators.md#op_eq_eq)|[operator = = (hash_multimap)](hash-map-operators.md#op_eq_eq_mm)|İşlecin sol tarafındaki hash_map veya hash_multimap nesnesinin sağ taraftaki hash_map veya hash_multimap nesnesine eşit olup olmadığını sınar.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Hash_map sürümü|Hash_multimap sürümü|Açıklama|
|-----------------------|----------------------------|-----------------|
|[swap (hash_map)](hash-map-class.md#swap)|[swap (hash_multimap)](hash-multimap-class.md#swap)|İki hash_maps veya hash_multimaps öğelerini değiş tokuş eder.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[hash_compare Sınıfı](hash-compare-class.md)|Hash_map, hash_multimap, hash_set veya hash_multiset gibi karma ilişkilendirilebilir kapsayıcılardan herhangi biri tarafından, içerdikleri öğeleri sıralamak ve karma hale getirmek için varsayılan bir `Traits` parametre nesnesi olarak kullanılabilecek bir nesneyi tanımlar.|
|[value_compare Sınıfı](value-compare-class.md)|, Hash_map içindeki göreli sıralarını belirleyebilmek için anahtarlarının değerlerini karşılaştırarak bir hash_map öğelerini karşılaştırabilen bir işlev nesnesi sağlar.|
|[hash_map Sınıfı](hash-map-class.md)|Her bir öğenin değeri benzersiz ve ilişkili bir veri değeri olan bir sıralama anahtarına sahip bir çiftin bulunduğu bir koleksiyondaki verilerin depolanması ve hızlı alımı için kullanılır.|
|[hash_multimap Sınıfı](hash-multimap-class.md)|Her öğenin, değeri benzersiz olmayan bir sıralama anahtarına ve ilişkili bir veri değerine sahip olan bir çiftin bulunduğu bir koleksiyondaki verilerin depolanması ve hızlı alımı için kullanılır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<hash_map >

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md) \
[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](cpp-standard-library-reference.md)
