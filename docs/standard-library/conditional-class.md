---
title: conditional Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::conditional
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
ms.openlocfilehash: b8f0f69cc1e4f6966bc9ccb63fe529436295badd
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457318"
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

*KENARI*\
Seçili türü belirleyen değer.

*T1*\
B doğru olduğunda tür sonucu.

*T2*\
B false olduğunda tür sonucu.

## <a name="remarks"></a>Açıklamalar

Şablon üyesi `conditional<B, T1, T2>::type` typedef, *b* **doğru**olarak değerlendirildiğinde *T1* olarak değerlendirilir ve *b* , **false**olduğunda *T2* olarak değerlendirilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
