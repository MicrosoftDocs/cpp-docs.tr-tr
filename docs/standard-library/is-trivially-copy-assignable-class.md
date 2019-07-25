---
title: is_trivially_copy_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
ms.openlocfilehash: c0019257a032d3becc268513336ed59e58a2e1d5
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448005"
---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable sınıfı

Türün bir Önemsiz kopya atama işlecine sahip olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* , Önemsiz kopya atama operatörü olan bir sınıf ise true, aksi takdirde false barındırır.

*Sınıf t* için atama Oluşturucusu, örtük olarak sağlanmışsa, *t* sınıfı sanal bir Işleve sahip değildir, *t* sınıfının sanal temeli yoktur, sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları ise önemsiz atamadır İşleçler ve sınıf dizisi türündeki tüm statik olmayan veri üyelerinin basit atama işleçleri vardır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
