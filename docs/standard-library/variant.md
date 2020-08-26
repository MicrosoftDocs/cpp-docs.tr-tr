---
title: '&lt;varyantı&gt;'
ms.date: 04/04/2019
f1_keywords:
- <variant>
helpviewer_keywords:
- <variant>
ms.openlocfilehash: 1a3c861c96fedb7ef95eec66f95888ddc092bed4
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835668"
---
# <a name="ltvariantgt"></a>&lt;varyantı&gt;

Bir değişken nesnesi bir değeri tutar ve yönetir. Değişken bir değer tutuyorsa, bu değerin türü, Variant öğesine verilen şablon bağımsız değişken türlerinden biri olmalıdır. Bu şablon bağımsız değişkenlerine alternatifler adı verilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<variant>

**Ad alanı:** std

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç = =](../standard-library/forward-list-operators.md#op_eq_eq)|İşlecin sol tarafındaki VARIANT nesnesinin, sağ taraftaki VARIANT nesnesine eşit olup olmadığını sınar.|
|[işleç! =](../standard-library/forward-list-operators.md#op_neq)|İşlecin sol tarafındaki VARIANT nesnesinin, sağ taraftaki VARIANT nesnesine eşit olup olmadığını sınar.|
|[işleç<](../standard-library/forward-list-operators.md#op_lt)|İşlecin sol tarafındaki VARIANT nesnesinin, sağ taraftaki VARIANT nesnesinden küçük olup olmadığını sınar.|
|[işleç<=](../standard-library/forward-list-operators.md#op_lt_eq)|İşlecin sol tarafındaki değişken nesnenin sağ taraftaki VARIANT nesnesinden küçük veya ona eşit olup olmadığını sınar.|
|[işleç>](../standard-library/forward-list-operators.md#op_gt)|İşlecin sol tarafındaki VARIANT nesnesinin, sağ taraftaki VARIANT nesnesinden büyük olup olmadığını sınar.|
|[işleç>=](../standard-library/forward-list-operators.md#op_lt_eq)|İşlecin sol tarafındaki değişken nesnenin sağ taraftaki VARIANT nesnesinden büyük veya ona eşit olup olmadığını sınar.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[Al](../standard-library/variant-functions.md#get)|Bir nesnenin türevini alır.|
|[get_if](../standard-library/variant-functions.md#get_if)|Varsa, bir nesnenin türevini alır.|
|[holds_alternative](../standard-library/variant-functions.md#holds_alternative)|**`true`** Bir değişken varsa döndürün.|
|[Kur](../standard-library/variant-functions.md#swap)|Bir **varyantı**değiştirir.|
|[ederken](../standard-library/variant-functions.md#visit)|Sonraki **varyanta**gider.|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|-|-|
|[bad_variant_access](../standard-library/bad-variant-access-class.md)|Bir değişken nesnesinin değerine geçersiz erişimi bildirmek için oluşturulan nesneler.|
|[varyantı](../standard-library/variant.md)|Bir nesne alternatif türlerinden birinin değerini tutacak veya hiçbir değer içermeyecek.|

### <a name="structs"></a>Yapılar

|Ad|Açıklama|
|-|-|
|[yla](../standard-library/hash-structure.md)||
|[monostate](../standard-library/monostate-structure.md)|Değişken türü varsayılan oluşturulabilir hale getirmek için bir varyant için alternatif tür.|
|[uses_allocator](../standard-library/uses-allocator-structure.md)||
|[variant_alternative](../standard-library/variant-alternative-structure.md)|Değişken nesnelerine yardımcı olur.|
|[variant_size](../standard-library/variant-size-structure.md)|Değişken nesnelerine yardımcı olur.|

### <a name="objects"></a>Nesneler

|Ad|Açıklama|
|-|-|
|[variant_npos](../standard-library/variant-functions.md#variant_npos)||

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
