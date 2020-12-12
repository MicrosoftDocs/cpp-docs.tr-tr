---
description: 'Hakkında daha fazla bilgi edinin: is_trivially_copy_assignable sınıfı'
title: is_trivially_copy_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
ms.openlocfilehash: 010e820db570f594568cb60f4edae83b91a997c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271245"
---
# <a name="is_trivially_copy_assignable-class"></a>is_trivially_copy_assignable sınıfı

Türün bir Önemsiz kopya atama işlecine sahip olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* , Önemsiz kopya atama operatörü olan bir sınıf ise true, aksi takdirde false barındırır.

Sınıf t için atama Oluşturucusu, örtük olarak sağlanmışsa, *t* sınıfı sanal bir işleve *sahip değildir,* *t* sınıfının sanal bir tabanı yoktur, sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz atama işleçlerine sahiptir ve sınıf dizisi türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz atama işleçleridir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
