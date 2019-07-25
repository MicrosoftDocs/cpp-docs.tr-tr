---
title: is_copy_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_copy_assignable
helpviewer_keywords:
- is_copy_assignable
ms.assetid: 3ae6bca1-85fb-4829-9ee9-0183b081ff50
ms.openlocfilehash: 5fedd32f026828e49ea29cb2975a2529ca28c862
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452835"
---
# <a name="iscopyassignable-class"></a>is_copy_assignable sınıfı

Tür, atamaya kopyalanıp kopyalanamayacağını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür değeri, kopya atama operatörü olan bir sınıfdaysa,  tür koşulunun bir örneği true, aksi takdirde false değerini taşır. İs_assignable\<Ty &, const Ty & > eşdeğerdir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
