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
ms.openlocfilehash: 57e01cbfd7cb291ff7d2651e3244b74ae96adbea
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962406"
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

*B* seçili türü belirleyen değer.

*T1* B true olduğunda türü sonucu.

*T2* B false olduğunda türü sonucu.

## <a name="remarks"></a>Açıklamalar

Şablon üye typedef `conditional<B, T1, T2>::type` değerlendiren *T1* olduğunda *B* değerlendiren **true**ve değerlendiren *T2* olduğunda  *B* değerlendiren **false**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
