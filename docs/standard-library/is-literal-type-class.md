---
title: is_literal_type sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_literal_type
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
ms.openlocfilehash: d5b750755f2499c89e91e497ed03244a11484871
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212260"
---
# <a name="is_literal_type-class"></a>is_literal_type sınıfı

Bir türün bir değişken olarak kullanılıp kullanılamayacağını **`constexpr`** , veya tarafından oluşturulup kullanılamayacağını veya işlevlerden döndürüldüğünü sınar **`constexpr`** .

## <a name="syntax"></a>Söz dizimi

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* türü, *sabit değer türünde*ise true, aksi takdirde false değerini taşır. Değişmez değer türü, **`void`** skaler bir tür, başvuru türü, bir sabit değer türü dizisi ya da değişmez sınıf türü. Sabit bir sınıf türü, önemsiz yok edicisi olan bir sınıf türüdür, bir toplam türüdür veya en az bir tane taşınamaz, kopya olmayan **`constexpr`** oluşturucuya ve tüm temel sınıflarının ve statik olmayan veri üyelerinin tümü geçici olmayan değişmez türlerdir. Bir sabit değerin türü her zaman değişmez bir tür olsa da, değişmez değer türü kavramı derleyicinin derleme zamanında değerlendirebildiği her şeyi içerir **`constexpr`** .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
