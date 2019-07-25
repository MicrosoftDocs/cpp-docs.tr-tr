---
title: is_literal_type sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_literal_type
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
ms.openlocfilehash: 450c32d050a18f64e71992bd7a30412ebafe93de
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456218"
---
# <a name="isliteraltype-class"></a>is_literal_type sınıfı

Bir türün bir `constexpr` değişken olarak kullanılıp kullanılamayacağını, veya tarafından oluşturulup kullanılamayacağını veya `constexpr` işlevlerden döndürüldüğünü sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* türü, *sabit değer türünde*ise true, aksi takdirde false değerini taşır. Değişmez değer türü **void**, skaler bir tür, bir başvuru türü, bir sabit değer türü dizisi ya da sabit sınıf türü. Sabit bir sınıf türü, önemsiz yok edicisi olan bir sınıf türüdür, bir toplam türüdür veya en az bir tane taşınamaz, kopya `constexpr` olmayan oluşturucuya ve tüm temel sınıflarının ve statik olmayan veri üyelerinin tümü geçici olmayan değişmez türlerdir. Bir sabit değerin türü her zaman değişmez bir tür olsa da, değişmez değer türü kavramı derleyicinin derleme zamanında değerlendirebildiği `constexpr` her şeyi içerir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
