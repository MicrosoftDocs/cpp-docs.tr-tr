---
description: 'Daha fazla bilgi edinin: EnableIf yapısı'
title: EnableIf Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
ms.openlocfilehash: 098dd5fdc7e37a7754d7124eba3e146575c127be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272857"
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
