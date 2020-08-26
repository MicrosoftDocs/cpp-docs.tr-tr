---
title: '&lt;optional&gt;'
ms.date: 08/06/2019
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.openlocfilehash: 31a3d9aad539e45bb835331a4ef63690d0e16f49
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842682"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

Kapsayıcı sınıfı şablonunu `optional` ve çeşitli destekleyici şablonları tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<optional>

**Ad alanı:** std

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç = =](../standard-library/optional-operators.md#op_eq_eq)|Bir nesnenin başka bir nesneye eşit olup olmadığını sınar.|
|[işleç! =](../standard-library/optional-operators.md#op_neq)|Bir nesnenin başka bir nesneye eşit olup olmadığını sınar.|
|[işleç<](../standard-library/optional-operators.md#op_lt)|Soldaki nesne sağdaki nesneden küçükse sınar.|
|[işleç<=](../standard-library/optional-operators.md#op_lt_eq)|Soldaki nesnenin sağdaki nesneden küçük veya ona eşit olup olmadığını sınar.|
|[işleç>](../standard-library/optional-operators.md#op_gt)|Soldaki nesnenin sağdaki nesneden daha büyük olup olmadığını sınar.|
|[işleç>=](../standard-library/optional-operators.md#op_lt_eq)|Soldaki nesnenin sağdaki nesneden büyük veya ona eşit olup olmadığını sınar.|

> [!NOTE]
> İlişkisel \<optional> karşılaştırmaların yanı sıra operatörler de **nullopt** ve ile karşılaştırmayı destekler `T` .

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|Bir nesneyi isteğe bağlı hale getirir.|
|[Kur](../standard-library/optional-functions.md#swap)|İki nesnenin içerilen değerlerini değiştirir `optional` .|

### <a name="classes-and-structs"></a>Sınıflar ve Yapılar

|Ad|Açıklama|
|-|-|
|hash|İçerilen nesnenin karmasını döndürür.|
|[isteğe bağlı sınıf](../standard-library/optional-class.md)|Bir değeri tutan veya tutabilecek bir nesneyi açıklar.|
|[nullopt_t yapısı](../standard-library/nullopt-t-structure.md)|Bir değeri tutan bir nesne tanımlar.|
|[bad_optional_access sınıfı](../standard-library/bad-optional-access-class.md)|Bir değere erişim denemesini raporlamak için bir özel durum olarak oluşturulan bir nesne tanımlar.|

### <a name="objects"></a>Nesneler

|Ad|Açıklama|
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)|`nullopt_t`Karşılaştırma için bir örnek.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
