---
description: 'Daha fazla bilgi edinin: InterfaceListHelper yapısı'
title: InterfaceListHelper Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceListHelper
helpviewer_keywords:
- InterfaceListHelper structure
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
ms.openlocfilehash: ca9e13e66acb6f27fba76a7653388305c57146dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249808"
---
# <a name="interfacelisthelper-structure"></a>InterfaceListHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    typename T0,
    typename T1 = Nil,
    typename T2 = Nil,
    typename T3 = Nil,
    typename T4 = Nil,
    typename T5 = Nil,
    typename T6 = Nil,
    typename T7 = Nil,
    typename T8 = Nil,
    typename T9 = Nil
>
struct InterfaceListHelper;

template <typename T0>
struct InterfaceListHelper<T0, Nil, Nil, Nil, Nil, Nil, Nil, Nil, Nil>;
```

### <a name="parameters"></a>Parametreler

*T0*<br/>
Şablon parametresi 0, gerekli.

*T1*<br/>
Varsayılan olarak belirtilmemiş olan şablon parametresi 1.

*T2*<br/>
Varsayılan olarak belirtilmemiş olan şablon parametresi 2. Üçüncü şablon parametresi.

*T3*<br/>
Varsayılan olarak belirtilmeyen şablon parametresi 3.

*T4*<br/>
Varsayılan olarak belirtilmemiş olan şablon parametresi 4.

*T5*<br/>
Varsayılan olarak belirtilmemiş olan şablon parametresi 5.

*T6*<br/>
Şablon parametresi 6, varsayılan olarak belirtilmemiş.

*T7*<br/>
Varsayılan olarak belirtilmemiş olan şablon parametresi 7.

*T8*<br/>
Varsayılan olarak belirtilmemiş olan şablon parametresi 8.

*T9*<br/>
Varsayılan olarak belirtilmemiş olan şablon parametresi 9.

## <a name="remarks"></a>Açıklamalar

`InterfaceList`Belirtilen şablon parametresi bağımsız değişkenlerini yinelemeli olarak uygulayarak bir tür oluşturur.

**InterfaceListHelper** Template, bir yapıdaki ilk veri üyesini tanımlamak için *T0* şablon parametresini kullanır `InterfaceList` ve ardından, yeniden kalan tüm şablon parametrelerine **InterfaceListHelper** şablonunu yinelemeli olarak uygular. **InterfaceListHelper** , kalan şablon parametreleri olmadığında durduruluyor.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`TypeT`|InterfaceList türü için bir eş anlamlı.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`InterfaceListHelper`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL::D euçlar ad alanı](microsoft-wrl-details-namespace.md)
