---
title: '&lt;Değişken&gt;'
ms.date: 04/04/2019
f1_keywords:
- <variant>
helpviewer_keywords:
- <variant>
ms.openlocfilehash: 7a812ccc3c8cb2a660c01ad2b17ea75b5d5c9542
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68267888"
---
# <a name="ltvariantgt"></a>&lt;Değişken&gt;

VARIANT nesnesi tutar ve bir değer yönetir. Değişken bir değeri tutar, bu değerin türü değişkenine verilen şablon bağımsız değişken türlerinden biri olması gerekir. Bu şablon bağımsız değişkenleri alternatifleri çağrılır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<değişken >

**Namespace:** std

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator==](../standard-library/forward-list-operators.md#op_eq_eq)|İşlecin sol tarafındaki VARIANT nesnesi işlecin sağ tarafındaki değişken nesneye eşit olup olmadığını sınar.|
|[operator!=](../standard-library/forward-list-operators.md#op_neq)|İşlecin sol tarafındaki VARIANT nesnesi işlecin sağ tarafındaki değişken nesneye eşit olup olmadığını sınar.|
|[işleç <](../standard-library/forward-list-operators.md#op_lt)|İşlecin sol tarafındaki VARIANT nesnesi işlecin sağ tarafındaki değişken nesneden küçük olup olmadığını sınar.|
|[operator < =](../standard-library/forward-list-operators.md#op_lt_eq)|Değişken işlecinin sol tarafında nesne küçük olup olmadığını sınar veya değişken nesneye eşitse işlecin sağ tarafındaki.|
|[operator >](../standard-library/forward-list-operators.md#op_gt)|İşlecin sol tarafındaki VARIANT nesnesi değişken nesnesinin işlecin sağ tarafındaki büyük olup olmadığını sınar.|
|[operator>=](../standard-library/forward-list-operators.md#op_lt_eq)|VARIANT nesnesi işlecinin sol tarafındaki büyük veya işlecin sağ tarafındaki değişken nesneye eşit olup olmadığını sınar.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[get](../standard-library/variant-functions.md#get)|Nesnenin çeşidini alır.|
|[get_if](../standard-library/variant-functions.md#get_if)|Varsa bir nesnenin değişken alır.|
|[holds_alternative](../standard-library/variant-functions.md#holds_alternative)|Dönüş **true** bir değişken zaten varsa.|
|[değiştirme](../standard-library/variant-functions.md#swap)|Değiştirir bir **değişken**.|
|[Ziyaret edin](../standard-library/variant-functions.md#visit)|Sonraki taşır **değişken**.|

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[bad_variant_access](../standard-library/bad-variant-access-class.md)|Nesneleri rapor geçersiz erişimin bir çeşit nesnenin değeri için oluşturulur.|
|[Değişken](../standard-library/variant.md)|Bir nesne ya da alternatif türlerinden veya değer değeri tutun.|

### <a name="structs"></a>Yapılar

|||
|-|-|
|[Karma](../standard-library/hash-structure.md)||
|[monostate](../standard-library/monostate-structure.md)|Bir alternatif türü için bir değişken değişken türü varsayılan atmamalıdır yapma.|
|[uses_allocator](../standard-library/uses-allocator-structure.md)||
|[variant_alternative](../standard-library/variant-alternative-structure.md)|Değişken nesneleri yardımcı olur.|
|[variant_size](../standard-library/variant-size-structure.md)|Değişken nesneleri yardımcı olur.|

### <a name="objects"></a>Nesneler

|||
|-|-|
|[variant_npos](../standard-library/variant-functions.md#variant_npos)||

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
