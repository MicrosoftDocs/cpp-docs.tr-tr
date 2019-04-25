---
title: '&lt;hash_map&gt;'
ms.date: 01/18/2018
f1_keywords:
- <hash_map>
- std::<hash_map>
helpviewer_keywords:
- hash_map header
ms.openlocfilehash: 5a7ea891a314d69b8bc3378edce9fa0de2d89ace
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159502"
---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;

> [!NOTE]
> Bu üst bilgi kullanılmıyor. Alternatif [ \<unordered_map >](unordered-map.md).

Kapsayıcı şablon sınıfları hash_map ve hash_multimap ve kendi destek şablonları tanımlar.

## <a name="syntax"></a>Sözdizimi

```
#include <hash_map>
```

### <a name="operators"></a>İşleçler

|Hash_map sürümü|Hash_multimap sürümü|Açıklama|
|-----------------------|----------------------------|-----------------|
|[işleç! = (hash_map)](hash-map-operators.md#op_neq)|[operator!=(hash_multimap)](hash-map-operators.md#op_neq_mm)|İşlecin sol tarafındaki hash_map veya hash_multimap nesne işlecin sağ tarafındaki hash_map veya hash_multimap nesneye eşit olup olmadığını sınar.|
|[işleç == (hash_map)](hash-map-operators.md#op_eq_eq)|[işleç == (hash_multimap)](hash-map-operators.md#op_eq_eq_mm)|İşlecin sol tarafındaki hash_map veya hash_multimap nesnesinin işlecin sağ tarafındaki hash_map veya hash_multimap nesneye eşit olup olmadığını sınar.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Hash_map sürümü|Hash_multimap sürümü|Açıklama|
|-----------------------|----------------------------|-----------------|
|[swap (hash_map)](hash-map-class.md#swap)|[swap (hash_multimap)](hash-multimap-class.md#swap)|İki hash_maps veya hash_multimaps öğelerini birbiriyle değiştirir.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[hash_compare Sınıfı](hash-compare-class.md)|Herhangi bir karma ilişkilendirilebilir kapsayıcılar tarafından kullanılabilen bir nesne tanımlayan — hash_map, hash_multimap, hash_set, veya hash_multiset — varsayılan olarak `Traits` sipariş ve içerdikleri öğelerin karma parametre nesnesi.|
|[value_compare Sınıfı](value-compare-class.md)|Hash_map kendi göreli sıralarını belirlemek için kendi anahtarını değerlerini karşılaştırarak bir hash_map öğelerini karşılaştıran bir işlev nesnesi sağlar.|
|[hash_map Sınıfı](hash-map-class.md)|Her bir öğenin değeri benzersiz olan sıralama anahtarına sahip olduğu bir çift olan bir koleksiyonu ve ilişkili veriler bir değer verileri hızlı alma ve depolama için kullanılır.|
|[hash_multimap Sınıfı](hash-multimap-class.md)|Her bir öğenin değerini benzersiz olması gerekmez sıralama anahtarına sahip olduğu bir çift olan bir koleksiyonu ve ilişkili veriler bir değer verileri hızlı alma ve depolama için kullanılır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<hash_map >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](cpp-standard-library-reference.md)
