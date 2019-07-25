---
title: '&lt;harita&gt;'
ms.date: 11/04/2016
f1_keywords:
- <map>
helpviewer_keywords:
- map header
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
ms.openlocfilehash: 3c3c7fc34e75772c10ba39ecc51f6d2ac59d7ad5
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456298"
---
# <a name="ltmapgt"></a>&lt;harita&gt;

Kapsayıcı şablon sınıfları haritasını ve multimap ve destekleyici şablonlarını tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<eşleme >

**Ad alanı:** std

> [!NOTE]
> Map > kitaplığı, `#include <initializer_list>` ifadesini de kullanır. \<

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|Eşleme sürümü|Multimap sürümü|Açıklama|
|-----------------|----------------------|-----------------|
|[işleç! = (eşleme)](../standard-library/map-operators.md#op_neq)|[işleç! = (multimap)](../standard-library/map-operators.md#op_neq)|İşlecin sol tarafındaki Map veya multimap nesnesinin sağ taraftaki Map veya multimap nesnesine eşit olmadığını test eder.|
|[işleç < (eşleme)](../standard-library/map-operators.md#op_eq_eq)|[işleç < (multimap)](../standard-library/map-operators.md#op_eq_eq)|İşlecin sol tarafındaki Map veya multimap nesnesinin sağ taraftaki Map veya multimap nesnesinden küçük olup olmadığını test eder.|
|[işleç < = (eşleme)](../standard-library/map-operators.md#op_lt)|[operator\<= (multimap)](../standard-library/map-operators.md#op_lt)|İşlecin sol tarafındaki Map veya multimap nesnesinin, sağ taraftaki Map veya multimap nesnesinden küçük veya ona eşit olup olmadığını sınar.|
|[işleç = = (eşleme)](../standard-library/map-operators.md#op_eq_eq)|[işleç = = (multimap)](../standard-library/map-operators.md#op_eq_eq_multimap)|İşlecin sol tarafındaki Map veya multimap nesnesinin sağ taraftaki Map veya multimap nesnesine eşit olup olmadığını sınar.|
|[işleç > (eşleme)](../standard-library/map-operators.md#op_gt)|[işleç > (multimap)](../standard-library/map-operators.md#op_gt_multimap)|İşlecin sol tarafındaki Map veya multimap nesnesinin sağ taraftaki Map veya multimap nesnesinden büyük olup olmadığını test eder.|
|[işleç > = (eşleme)](../standard-library/map-operators.md#op_gt_eq)|[işleç > = (multimap)](../standard-library/map-operators.md#op_gt_eq_multimap)|İşlecin sol tarafındaki harita veya multimap nesnesinin sağ taraftaki Map veya multimap nesnesinden büyük veya ona eşit olup olmadığını sınar.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Eşleme sürümü|Multimap sürümü|Açıklama|
|-----------------|----------------------|-----------------|
|[swap (eşleme)](../standard-library/map-functions.md#swap)|[takas (multimap)](../standard-library/map-functions.md#swap_multimap)|İki harita veya birden çok haritalar için öğeleri değiş tokuş eder.|

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[value_compare Sınıfı](../standard-library/value-compare-class-map.md)|Haritadaki göreli sıralarını tespit etmek için anahtarlarının değerlerini karşılaştırarak bir haritanın öğelerini karşılaştırabilen bir işlev nesnesi sağlar.|
|[map Sınıfı](../standard-library/map-class.md)|Öğelerin her birinde verilerin otomatik olarak sıralandığı benzersiz bir anahtara sahip olduğu bir koleksiyondan verilerin depolanması ve alınması için kullanılır.|
|[multimap Sınıfı](../standard-library/multimap-class.md)|Öğelerin her birinin, verilerin otomatik olarak sıralandığı ve anahtarların benzersiz değerlere sahip olması gereken bir anahtara sahip olduğu bir koleksiyondan verilerin depolanması ve alınması için kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
