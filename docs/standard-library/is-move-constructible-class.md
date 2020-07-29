---
title: is_move_constructible sınıfı
ms.date: 10/24/2019
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: 5495ac39a98f5c194f19d28ba85a1d59f47dfbb4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222387"
---
# <a name="is_move_constructible-class"></a>is_move_constructible sınıfı

Türün bir taşıma işlemi kullanılarak oluşturulup oluşturulmayacağını sınar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Değerlendirilecek tür.

## <a name="remarks"></a>Açıklamalar

**`true`** Tür *T* bir taşıma işlemi kullanılarak oluşturulabilmesidir olarak değerlendirilen bir tür koşulu. Bu koşul ile eşdeğerdir `is_constructible<T, T&&>` . Taşıma oluşturucusuna sahip olmayan, ancak bağımsız değişken kabul eden bir kopya Oluşturucusu olan bir tür *T* `const T&` `std::is_move_constructible` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
