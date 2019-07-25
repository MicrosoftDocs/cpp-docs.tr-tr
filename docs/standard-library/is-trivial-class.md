---
title: is_trivial sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivial
helpviewer_keywords:
- is_trivial
ms.assetid: 6beb11d4-2f38-4c7e-9959-ca5d26250df7
ms.openlocfilehash: 1d218848fd65ca68022e3e66df02201582626711
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457428"
---
# <a name="istrivial-class"></a>is_trivial sınıfı

Türün önemsiz bir tür olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_trivial;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür olarak bir örnek, tür *T* önemsiz bir tür ise true, aksi takdirde false barındırır. Önemsiz türler skaler türlerdir, Üçlü kopyalanabilir sınıf türleridir, bu türlerin dizileri ve bu türlerin CV nitelikli sürümleridir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
