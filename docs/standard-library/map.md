---
title: '&lt;Harita&gt;'
ms.date: 11/04/2016
f1_keywords:
- <map>
helpviewer_keywords:
- map header
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
ms.openlocfilehash: 0ea47a28599df543987831ee13a2c645f72a0113
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413001"
---
# <a name="ltmapgt"></a>&lt;Harita&gt;

Kapsayıcı şablon sınıfları harita ve multimap ve kendi destek şablonları tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <map>
```

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|Harita sürümü|Multimap sürümü|Açıklama|
|-----------------|----------------------|-----------------|
|[işleç! = (map)](../standard-library/map-operators.md#op_neq)|[işleç! = (multimap)](../standard-library/map-operators.md#op_neq)|İşlecin sol tarafındaki eşlemesi veya multimap nesne eşlemesi veya multimap nesnesinin işlecin sağ tarafındaki eşit olup olmadığını sınar.|
|[operator < (map)](../standard-library/map-operators.md#op_eq_eq)|[operator < (multimap)](../standard-library/map-operators.md#op_eq_eq)|İşlecin sol tarafındaki eşlemesi veya multimap nesne işlecin sağ tarafındaki eşlemesi veya multimap nesneden küçük olup olmadığını sınar.|
|[operator < = (map)](../standard-library/map-operators.md#op_lt)|[İşleç\<= (multimap)](../standard-library/map-operators.md#op_lt)|Harita veya multimap nesne işlecinin sol tarafındaki küçüktür veya eşittir harita veya işlecin sağ tarafındaki multimap nesne olup olmadığını sınar.|
|[işleç == (map)](../standard-library/map-operators.md#op_eq_eq)|[işleç == (multimap)](../standard-library/map-operators.md#op_eq_eq_multimap)|İşlecin sol tarafındaki eşlemesi veya multimap nesnesinin işlecin sağ tarafındaki eşlemesi veya multimap nesneye eşitse olup olmadığını sınar.|
|[operator > (map)](../standard-library/map-operators.md#op_gt)|[operator > (multimap)](../standard-library/map-operators.md#op_gt_multimap)|İşlecin sol tarafındaki eşlemesi veya multimap nesne eşlemesi veya multimap nesnesinin işlecin sağ tarafındaki büyük olup olmadığını sınar.|
|[operator > = (map)](../standard-library/map-operators.md#op_gt_eq)|[operator > = (multimap)](../standard-library/map-operators.md#op_gt_eq_multimap)|Harita veya multimap nesne işlecinin sol tarafındaki büyük veya işlecin sağ tarafındaki eşlemesi veya multimap nesneye eşit olup olmadığını sınar.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Harita sürümü|Multimap sürümü|Açıklama|
|-----------------|----------------------|-----------------|
|[Swap (map)](../standard-library/map-functions.md#swap)|[Swap (multimap)](../standard-library/map-functions.md#swap_multimap)|İki haritalar veya multimaps öğelerini birbiriyle değiştirir.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[value_compare Sınıfı](../standard-library/value-compare-class-map.md)|Bir eşlemin öğelerini haritadaki kendi göreli sıralarını belirlemek için anahtarlarına değerlerini karşılaştırarak karşılaştıran bir işlev nesnesi sağlar.|
|[map Sınıfı](../standard-library/map-class.md)|Öğelerin her biri benzersiz bir anahtar ile verilerin otomatik sıralamasına sahip bir koleksiyondaki verileri alma ve depolama için kullanılır.|
|[multimap Sınıfı](../standard-library/multimap-class.md)|Öğelerin her biri hangi verileri otomatik olarak sıralanır ve anahtarları, benzersiz değerlere sahip gerekmez. bir anahtarı olan bir koleksiyondaki verileri alma ve depolama için kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
