---
description: 'Daha fazla bilgi edinin: koşullu sınıf'
title: conditional Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::conditional
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
ms.openlocfilehash: f8edbd7341598957ecbe8b0822a832973f0e06a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324977"
---
# <a name="conditional-class"></a>conditional Sınıfı

Belirtilen koşula göre, iki türden birini seçer.

## <a name="syntax"></a>Sözdizimi

```cpp
template <bool B, class T1, class T2>
struct conditional;

template <bool _Test, class _T1, class _T2>
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```

### <a name="parameters"></a>Parametreler

*Kenarı*\
Seçili türü belirleyen değer.

*T1*\
B doğru olduğunda tür sonucu.

*T2*\
B false olduğunda tür sonucu.

## <a name="remarks"></a>Açıklamalar

Şablon üyesi typedef, `conditional<B, T1, T2>::type` *b* olarak değerlendirildiğinde *T1* olarak değerlendirilir **`true`** ve *b* tarafından değerlendirildiğinde *T2* olarak değerlendirilir **`false`** .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
