---
title: InterfaceListHelper Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceListHelper
helpviewer_keywords:
- InterfaceListHelper structure
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
ms.openlocfilehash: 1a7b4c19bbcdd4161e9078274f18f96a48f9e7d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213856"
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

Belirtilen şablon parametresi bağımsız değişkenlerini yinelemeli olarak uygulayarak bir `InterfaceList` türü oluşturur.

**InterfaceListHelper** şablonu, bir `InterfaceList` yapısındaki ilk veri üyesini tanımlamak için *T0* şablon parametresini kullanır ve ardından, geri kalan tüm şablon parametrelerine **InterfaceListHelper** şablonunu yinelemeli olarak uygular. **InterfaceListHelper** , kalan şablon parametreleri olmadığında durduruluyor.

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

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)
