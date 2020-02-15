---
title: '&lt;hash_map&gt;'
ms.date: 01/18/2018
f1_keywords:
- <hash_map>
- std::<hash_map>
helpviewer_keywords:
- hash_map header
ms.openlocfilehash: 6bb2ca0cc14bcc4a9b9df9877902de9181e0a768
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77258152"
---
# <a name="lthash_mapgt"></a>&lt;hash_map&gt;

> [!NOTE]
> Bu üst bilgi artık kullanılmıyor. Alternatif, [> unordered_map\<](unordered-map.md).

Kapsayıcı sınıfı şablonları hash_map ve hash_multimap ve destekleyici şablonlarını tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <hash_map>
```

### <a name="operators"></a>İşleçler

|Hash_map sürümü|Hash_multimap sürümü|Açıklama|
|-----------------------|----------------------------|-----------------|
|[işleç! = (hash_map)](hash-map-operators.md#op_neq)|[işleç! = (hash_multimap)](hash-map-operators.md#op_neq_mm)|İşlecin sol tarafındaki hash_map veya hash_multimap nesnesinin sağ taraftaki hash_map veya hash_multimap nesnesine eşit olmadığını sınar.|
|[işleç = = (hash_map)](hash-map-operators.md#op_eq_eq)|[işleç = = (hash_multimap)](hash-map-operators.md#op_eq_eq_mm)|İşlecin sol tarafındaki hash_map veya hash_multimap nesnesinin sağ taraftaki hash_map veya hash_multimap nesnesine eşit olup olmadığını sınar.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Hash_map sürümü|Hash_multimap sürümü|Açıklama|
|-----------------------|----------------------------|-----------------|
|[takas (hash_map)](hash-map-class.md#swap)|[takas (hash_multimap)](hash-multimap-class.md#swap)|İki hash_maps veya hash_multimaps öğelerini değiş tokuş eder.|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[hash_compare Sınıfı](hash-compare-class.md)|Hash_map, hash_multimap, hash_set veya hash_multiset, içerdikleri öğeleri sıralamak ve karma hale getirmek için varsayılan bir `Traits` parametre nesnesi olarak kullanılabilecek bir nesne tanımlar.|
|[value_compare Sınıfı](value-compare-class.md)|Hash_map öğelerini, hash_map göreli sıralarını belirleyerek kendi anahtar değerlerini karşılaştırarak karşılaştırabilen bir işlev nesnesi sağlar.|
|[hash_map Sınıfı](hash-map-class.md)|Her bir öğenin değeri benzersiz ve ilişkili bir veri değeri olan bir sıralama anahtarına sahip bir çiftin bulunduğu bir koleksiyondaki verilerin depolanması ve hızlı alımı için kullanılır.|
|[hash_multimap Sınıfı](hash-multimap-class.md)|Her öğenin, değeri benzersiz olmayan bir sıralama anahtarına ve ilişkili bir veri değerine sahip olan bir çiftin bulunduğu bir koleksiyondaki verilerin depolanması ve hızlı alımı için kullanılır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<hash_map >

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md)\
[Standart kitaplıkta Iş parçacığı güvenliği\ C++ ](thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](cpp-standard-library-reference.md)
