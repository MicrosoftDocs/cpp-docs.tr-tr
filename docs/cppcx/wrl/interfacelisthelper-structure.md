---
title: InterfaceListHelper Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceListHelper
helpviewer_keywords:
- InterfaceListHelper structure
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
ms.openlocfilehash: 03bfed00147daef22fe91e6f061ea6720834090f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025117"
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
Gerekli şablon parametresi, 0.

*T1*<br/>
Belirtilmezse, varsayılan şablon parametresi 1.

*T2*<br/>
Belirtilmezse, varsayılan şablon parametresi 2 '. Üçüncü şablon parametresi.

*T3*<br/>
Belirtilmezse, varsayılan şablon parametresi, 3.

*T4*<br/>
Belirtilmezse, varsayılan şablon parametresi, 4.

*T5*<br/>
Belirtilmezse, varsayılan şablon parametresi, 5.

*T6*<br/>
Belirtilmezse, varsayılan şablon parametresi, 6.

*T7*<br/>
Belirtilmezse, varsayılan şablon parametresi, 7.

*T8*<br/>
Belirtilmezse, varsayılan şablon parametresi 8.

*T9*<br/>
Belirtilmezse, varsayılan şablon parametresi 9.

## <a name="remarks"></a>Açıklamalar

Oluşturur bir `InterfaceList` yinelemeli olarak belirtilen şablon parametre bağımsız uygulama tarafından türü.

**Interfacelisthelper** şablon parametresi şablonu kullanan *T0* ilk veri üyesi tanımlamak için bir `InterfaceList` yapısı ve yinelemeli olarak geçerlidir  **Interfacelisthelper** kalan herhangi bir şablon parametre şablonu. **Interfacelisthelper** kalan şablon parametre bulunmadığında durdurur.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`TypeT`|Interfacelist türe ilişkin bir eşanlam.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`InterfaceListHelper`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)