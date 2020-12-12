---
description: 'Hakkında daha fazla bilgi edinin: is_trivially_copy_constructible sınıfı'
title: is_trivially_copy_constructible Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
ms.openlocfilehash: c247e81f52ad98e546a840bb38938fe15bc9b302
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118530"
---
# <a name="is_trivially_copy_constructible-class"></a>is_trivially_copy_constructible Sınıfı

Türün Önemsiz kopya oluşturucusuna sahip olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* bir örneği Önemsiz kopya oluşturucusuna sahip bir sınıf ise true, aksi takdirde false barındırır.

*Sınıf t* için bir kopya Oluşturucu örtük olarak bildirilirse, sınıf *t* 'nin sanal işlevleri veya sanal tabanlara sahip olmadığı *, t sınıfı* için tüm doğrudan temellerin ise Önemsiz kopya oluşturucuları vardır, sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları Önemsiz kopya oluşturucuları vardır ve sınıf dizisi türündeki tüm statik olmayan veri üyelerinin sınıfları, Önemsiz kopya oluşturucuları vardır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
