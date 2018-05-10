---
title: Conditional sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::conditional
dev_langs:
- C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d51397080267dd50f012b274e95ac4c9aa4fa64
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
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

`B` Seçili türünü belirleyen değeri.

`T1` B true olduğunda türü sonucu.

`T2` B false olduğunda türü sonucu.

## <a name="remarks"></a>Açıklamalar

Şablon üye typedef `conditional<B, T1, T2>::type` değerlendiren `T1` zaman `B` değerlendiren `true`ve değerlendiren `T2` zaman `B` değerlendiren `false`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
