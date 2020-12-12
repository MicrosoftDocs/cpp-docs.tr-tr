---
description: 'Hakkında daha fazla bilgi edinin: is_move_assignable sınıfı'
title: is_move_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_assignable
helpviewer_keywords:
- is_move_assignable
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
ms.openlocfilehash: ccca3eb1da646bad9e55222a23b5ae8d511d3bb3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230867"
---
# <a name="is_move_assignable-class"></a>is_move_assignable sınıfı

Tür atanmış olarak taşınabileceği test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Türe bir rvalue başvurusu, türe bir başvuruya atanabileceği takdirde tür atanabilir. Tür koşulu ile eşdeğerdir `is_assignable<T&, T&&>` . Atanabilir türleri, derleyici tarafından oluşturulan veya Kullanıcı tanımlı taşıma atama işleçleri olan başvurulabilir skaler türlerini ve sınıf türlerini içerir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
