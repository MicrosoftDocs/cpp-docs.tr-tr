---
description: 'Hakkında daha fazla bilgi edinin: is_move_constructible sınıfı'
title: is_move_constructible sınıfı
ms.date: 10/24/2019
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: 05ef640b2841eb3ab66f6d5a6d3b8ede7acf2754
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323639"
---
# <a name="is_move_constructible-class"></a>is_move_constructible sınıfı

Türün bir taşıma işlemi kullanılarak oluşturulup oluşturulmayacağını sınar.

## <a name="syntax"></a>Sözdizimi

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
