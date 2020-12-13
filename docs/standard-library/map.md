---
description: 'Daha fazla bilgi edinin: &lt; eşleme&gt;'
title: '&lt;harita&gt;'
ms.date: 11/04/2016
f1_keywords:
- <map>
helpviewer_keywords:
- map header
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
ms.openlocfilehash: 78a4afca400239b7f45637ad6320cbd950d72f54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149415"
---
# <a name="ltmapgt"></a>&lt;harita&gt;

Kapsayıcı sınıfı şablonları haritasını ve multimap ve destekleyici şablonlarını tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<map>

**Ad alanı:** std

> [!NOTE]
> \<map>Kitaplık, ifadesini de kullanır `#include <initializer_list>` .

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|Eşleme sürümü|Multimap sürümü|Açıklama|
|-----------------|----------------------|-----------------|
|[işleç! = (eşleme)](../standard-library/map-operators.md#op_neq)|[işleç! = (multimap)](../standard-library/map-operators.md#op_neq)|İşlecin sol tarafındaki Map veya multimap nesnesinin sağ taraftaki Map veya multimap nesnesine eşit olmadığını test eder.|
|[işleç< (eşleme)](../standard-library/map-operators.md#op_eq_eq)|[işleç< (multimap)](../standard-library/map-operators.md#op_eq_eq)|İşlecin sol tarafındaki Map veya multimap nesnesinin sağ taraftaki Map veya multimap nesnesinden küçük olup olmadığını test eder.|
|[işleç<= (eşleme)](../standard-library/map-operators.md#op_lt)|[operator \< = (multimap)](../standard-library/map-operators.md#op_lt)|İşlecin sol tarafındaki Map veya multimap nesnesinin, sağ taraftaki Map veya multimap nesnesinden küçük veya ona eşit olup olmadığını sınar.|
|[işleç = = (eşleme)](../standard-library/map-operators.md#op_eq_eq)|[işleç = = (multimap)](../standard-library/map-operators.md#op_eq_eq_multimap)|İşlecin sol tarafındaki Map veya multimap nesnesinin sağ taraftaki Map veya multimap nesnesine eşit olup olmadığını sınar.|
|[işleç> (eşleme)](../standard-library/map-operators.md#op_gt)|[işleç> (multimap)](../standard-library/map-operators.md#op_gt_multimap)|İşlecin sol tarafındaki Map veya multimap nesnesinin sağ taraftaki Map veya multimap nesnesinden büyük olup olmadığını test eder.|
|[işleç>= (eşleme)](../standard-library/map-operators.md#op_gt_eq)|[işleç>= (multimap)](../standard-library/map-operators.md#op_gt_eq_multimap)|İşlecin sol tarafındaki harita veya multimap nesnesinin sağ taraftaki Map veya multimap nesnesinden büyük veya ona eşit olup olmadığını sınar.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Eşleme sürümü|Multimap sürümü|Açıklama|
|-----------------|----------------------|-----------------|
|[swap (eşleme)](../standard-library/map-functions.md#swap)|[takas (multimap)](../standard-library/map-functions.md#swap_multimap)|İki harita veya birden çok haritalar için öğeleri değiş tokuş eder.|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|-|-|
|[value_compare sınıfı](../standard-library/value-compare-class-map.md)|Haritadaki göreli sıralarını tespit etmek için anahtarlarının değerlerini karşılaştırarak bir haritanın öğelerini karşılaştırabilen bir işlev nesnesi sağlar.|
|[Map sınıfı](../standard-library/map-class.md)|Öğelerin her birinde verilerin otomatik olarak sıralandığı benzersiz bir anahtara sahip olduğu bir koleksiyondan verilerin depolanması ve alınması için kullanılır.|
|[multimap sınıfı](../standard-library/multimap-class.md)|Öğelerin her birinin, verilerin otomatik olarak sıralandığı ve anahtarların benzersiz değerlere sahip olması gereken bir anahtara sahip olduğu bir koleksiyondan verilerin depolanması ve alınması için kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
