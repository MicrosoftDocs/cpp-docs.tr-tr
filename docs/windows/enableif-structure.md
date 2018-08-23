---
title: Enableıf yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
dev_langs:
- C++
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0e71c43ca9222b350c07dae5f299f4a6f469bf84
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42578563"
---
# <a name="enableif-structure"></a>EnableIf Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   bool b,
   typename T = void
>

struct EnableIf;
template <
   typename T
>
struct EnableIf<true, T>;
```

### <a name="parameters"></a>Parametreler

*T*  
Bir tür.

*b*  
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

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)