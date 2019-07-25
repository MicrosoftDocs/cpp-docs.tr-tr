---
title: is_move_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: c83ed4365fd0e73a7daa8b9894c5e85f20387a79
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456110"
---
# <a name="ismoveconstructible-class"></a>is_move_constructible sınıfı

Türün bir taşıma oluşturucusuna sahip olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Değerlendirilecek tür

## <a name="remarks"></a>Açıklamalar

Tür *T* bir taşıma işlemi kullanılarak oluşturulabiliyorsa true olarak değerlendirilen bir tür koşulu. Bu koşul ile `is_constructible<T, T&&>`eşdeğerdir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
