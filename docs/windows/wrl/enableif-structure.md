---
title: EnableIf Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
ms.openlocfilehash: 7b65b11b9a67ba69ca546e9bf5c169f3f2b61765
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335211"
---
# <a name="enableif-structure"></a>EnableIf Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <bool b, typename T = void>
struct EnableIf;

template <typename T>
struct EnableIf<true, T>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Bir tür.

*b*<br/>
Bir Boolean ifadesi.

## <a name="remarks"></a>Açıklamalar

İlk şablon parametresi değerlendirilirse ikinci şablon parametresi tarafından belirtilen türde bir veri üyesi tanımlar **true**.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`type`|Şablon parametresi *b* değerlendiren **true**, kısmi özelleştirmesi veri üyesi tanımlar `type` türünde olmasını `T`.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`EnableIf`

## <a name="requirements"></a>Gereksinimler

**Başlık:** internal.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)