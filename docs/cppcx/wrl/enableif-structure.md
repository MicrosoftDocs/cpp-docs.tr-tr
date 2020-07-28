---
title: EnableIf Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
ms.openlocfilehash: f43166920f3582ab681b67d2c89563dcf78ff0f1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220502"
---
# <a name="enableif-structure"></a>EnableIf Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <bool b, typename T = void>
struct EnableIf;

template <typename T>
struct EnableIf<true, T>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Bir tür.

*kenarı*<br/>
Boole ifadesi.

## <a name="remarks"></a>Açıklamalar

İlk şablon parametresi olarak değerlendirilirse ikinci şablon parametresi tarafından belirtilen türün veri üyesini tanımlar **`true`** .

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`type`|*B* şablon parametresi olarak değerlendirilirse **`true`** , kısmi `type` özelleşme veri üyesini türünden olacak şekilde tanımlar `T` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`EnableIf`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** iç. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL::D euçlar ad alanı](microsoft-wrl-details-namespace.md)
