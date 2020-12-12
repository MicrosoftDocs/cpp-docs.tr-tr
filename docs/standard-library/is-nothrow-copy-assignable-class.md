---
description: 'Hakkında daha fazla bilgi edinin: is_nothrow_copy_assignable sınıfı'
title: is_nothrow_copy_assignable Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
ms.openlocfilehash: 43618158e33a393012a9f7a4a3ad14c816e3cd6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230815"
---
# <a name="is_nothrow_copy_assignable-class"></a>is_nothrow_copy_assignable Sınıfı

Türün, derleyicinin throw olarak bilinen bir kopya atama işlecine sahip olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür koşulunun bir örneği, doğru tutan bir ReferenceType *T* için true, `is_nothrow_assignable<T&, const T&>` Aksi durumda false değerini tutar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[is_nothrow_assignable sınıfı](../standard-library/is-nothrow-assignable-class.md)
