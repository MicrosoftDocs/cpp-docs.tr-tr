---
title: is_trivially_copy_constructible Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
ms.openlocfilehash: f8c4026da424e77b57555dd4c342c9ac7a386591
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447987"
---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible Sınıfı

Türün Önemsiz kopya oluşturucusuna sahip olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* bir örneği Önemsiz kopya oluşturucusuna sahip bir sınıf ise true, aksi takdirde false barındırır.

*Sınıf t* için bir kopya Oluşturucu örtük olarak bildirilirse, *t* sınıfı, sanal işlevleri veya sanal tabanlara sahip değildir, t sınıfının tüm doğrudan temellerine, tüm statik olmayan veri üyelerinin sınıfları, Önemsiz kopya *oluşturucuları vardır.* sınıf türünün Önemsiz kopya oluşturucuları vardır ve sınıf dizisi türündeki tüm statik olmayan veri üyelerinin sınıfları Önemsiz kopya oluşturucuları vardır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
