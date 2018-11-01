---
title: is_nothrow_copy_assignable Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
ms.openlocfilehash: bb3aca47b61bdcc5b28eeedc1a6b4edefc303c4e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50583761"
---
# <a name="isnothrowcopyassignable-class"></a>is_nothrow_copy_assignable Sınıfı

Tür için derleyici throw değil bilinen kopya atama işlecine sahip olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

İçin önerebileceğimiz bir tür karşılaştırmasının bir örneği korumadıkça *T* burada `is_nothrow_assignable<T&, const T&>` true; Aksi takdirde false tuttuğu tutar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_nothrow_assignable Sınıfı](../standard-library/is-nothrow-assignable-class.md)<br/>
