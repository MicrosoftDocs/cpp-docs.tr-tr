---
title: is_move_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_assignable
helpviewer_keywords:
- is_move_assignable
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
ms.openlocfilehash: 8563db51eeb1988697b3e07a1a8673a777783e38
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456127"
---
# <a name="ismoveassignable-class"></a>is_move_assignable sınıfı

Tür atanmış olarak taşınabileceği test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Türe bir rvalue başvurusu, türe bir başvuruya atanabileceği takdirde tür atanabilir. Tür koşulu ile `is_assignable<T&, T&&>`eşdeğerdir. Atanabilir türleri, derleyici tarafından oluşturulan veya Kullanıcı tanımlı taşıma atama işleçleri olan başvurulabilir skaler türlerini ve sınıf türlerini içerir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
