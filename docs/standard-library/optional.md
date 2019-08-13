---
title: '&lt;optional&gt;'
ms.date: 08/06/2019
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.openlocfilehash: f3b4896a3cb4774e46b36480dd9769fa131fc287
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957171"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

Kapsayıcı şablonu sınıfını `optional` ve çeşitli destekleyici şablonları tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<isteğe bağlı >

**Ad alanı:** std

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator==](../standard-library/optional-operators.md#op_eq_eq)|Bir nesnenin başka bir nesneye eşit olup olmadığını sınar.|
|[operator!=](../standard-library/optional-operators.md#op_neq)|Bir nesnenin başka bir nesneye eşit olup olmadığını sınar.|
|[işleç <](../standard-library/optional-operators.md#op_lt)|Soldaki nesne sağdaki nesneden küçükse sınar.|
|[işleç < =](../standard-library/optional-operators.md#op_lt_eq)|Soldaki nesnenin sağdaki nesneden küçük veya ona eşit olup olmadığını sınar.|
|[işleç >](../standard-library/optional-operators.md#op_gt)|Soldaki nesnenin sağdaki nesneden daha büyük olup olmadığını sınar.|
|[operator>=](../standard-library/optional-operators.md#op_lt_eq)|Soldaki nesnenin sağdaki nesneden büyük veya ona eşit olup olmadığını sınar.|

> [!NOTE]
> İlişkisel karşılaştırmaların yanı sıra, \<isteğe bağlı > işleçleri de **nullopt** ve `T`ile karşılaştırmayı destekler.

### <a name="functions"></a>İşlevler

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|Bir nesneyi isteğe bağlı hale getirir.|
|[Kur](../standard-library/optional-functions.md#swap)|İki `optional` nesnenin içerilen değerlerini değiştirir.|

### <a name="classes-and-structs"></a>Sınıflar ve Yapılar

|||
|-|-|
|hash|İçerilen nesnenin karmasını döndürür.|
|[isteğe bağlı sınıf](../standard-library/optional-class.md)|Bir değeri tutan veya tutabilecek bir nesneyi açıklar.|
|[nullopt_t yapısı](../standard-library/nullopt-t-structure.md)|Bir değeri tutan bir nesne tanımlar.|
|[bad_optional_access sınıfı](../standard-library/bad-optional-access-class.md)|Bir değere erişim denemesini raporlamak için bir özel durum olarak oluşturulan bir nesne tanımlar.|

### <a name="objects"></a>Nesneler

|||
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)|Karşılaştırma `nullopt_t` için bir örnek.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
