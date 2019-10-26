---
title: is_move_constructible sınıfı
ms.date: 10/24/2019
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: 9585a932a34a24769201aaa379525a9b4c181e41
ms.sourcegitcommit: 33a898bf976c65f998b4e88a84765a0cef4193a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920099"
---
# <a name="is_move_constructible-class"></a>is_move_constructible sınıfı

Türün bir taşıma işlemi kullanılarak oluşturulup oluşturulmayacağını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parametreler

*T* \
Değerlendirilecek tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* bir taşıma işlemi kullanılarak oluşturulabiliyorsa **true** olarak değerlendirilen bir tür koşulu. Bu koşul `is_constructible<T, T&&>`eşdeğerdir. Taşıma oluşturucusuna sahip olmayan, ancak bir `const T&` bağımsız değişkenini kabul eden bir kopya Oluşturucusu olan bir tür *T* , `std::is_move_constructible`karşılar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
