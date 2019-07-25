---
title: '&lt;optional&gt;'
ms.date: 11/04/2016
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.assetid: 8b4ab09e-1475-434a-b4e0-fdbc07a08b5b
ms.openlocfilehash: 83a0ad52735f92d731dafb32ad1be5a8278776b4
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447177"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

İsteğe bağlı kapsayıcı şablonu sınıfını ve çeşitli destekleyici şablonları tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<isteğe bağlı >

**Ad alanı:** std

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator==](../standard-library/optional-operators.md#op_eq_eq)|İşlecin sol tarafındaki `optional` nesnenin sağ taraftaki `optional` nesneye eşit olup olmadığını sınar.|
|[operator!=](../standard-library/optional-operators.md#op_neq)|İşlecin sol tarafındaki `optional` nesnenin sağ taraftaki `optional` nesneye eşit olup olmadığını sınar.|
|[işleç <](../standard-library/optional-operators.md#op_lt)|İşlecin sol tarafındaki `optional` nesnenin sağ taraftaki `optional` nesneden daha az olup olmadığını sınar.|
|[işleç < =](../standard-library/optional-operators.md#op_lt_eq)|İşlecin sol tarafındaki `optional` nesnenin sağ taraftaki `optional` nesneden küçük veya ona eşit olup olmadığını sınar.|
|[işleç >](../standard-library/optional-operators.md#op_gt)|İşlecin sol tarafındaki `optional` nesnenin sağ taraftaki `optional` nesneden daha büyük olup olmadığını sınar.|
|[operator>=](../standard-library/optional-operators.md#op_lt_eq)|İşlecin sol tarafındaki `optional` nesnenin sağ taraftaki `optional` nesneden büyük veya ona eşit olup olmadığını sınar.|

> [!NOTE]
> İlişkisel karşılaştırmaların yanı sıra, \<isteğe bağlı > işleçleri de **nullopt** ve `T`ile karşılaştırmayı destekler.

### <a name="functions"></a>İşlevler

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|Bir nesneyi isteğe bağlı hale getirir.|
|[Kur](../standard-library/optional-functions.md#swap)||

### <a name="classes-and-structs"></a>Sınıflar ve Yapılar

|||
|-|-|
|[yla]()||
|[isteğe bağlı sınıf](../standard-library/optional-class.md)|Bir değeri tutan veya tutabilecek bir nesneyi açıklar.|
|[nullopt_t yapısı](../standard-library/nullopt-t-structure.md)|Bir değeri tutan bir nesne tanımlar.|
|[bad_optional_access sınıfı](../standard-library/bad-optional-access-class.md)|Bir değere erişim denemesini raporlamak için bir özel durum olarak oluşturulan bir nesne tanımlar.|

### <a name="objects"></a>Nesneler

|||
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)||

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
