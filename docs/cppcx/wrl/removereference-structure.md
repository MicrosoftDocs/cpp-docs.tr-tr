---
description: 'Daha fazla bilgi edinin: RemoveReference yapısı'
title: RemoveReference Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RemoveReference
helpviewer_keywords:
- RemoveReference structure
ms.assetid: 43ff91bb-815a-440e-b9fb-7dcbb7c863af
ms.openlocfilehash: 0bcf3685e44b756ce324adc8301d7afb5b4b3f40
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332500"
---
# <a name="removereference-structure"></a>RemoveReference Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
struct RemoveReference;

template<class T>
struct RemoveReference<T&>;

template<class T>
struct RemoveReference<T&&>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Bir sınıf.

## <a name="remarks"></a>Açıklamalar

Belirtilen sınıf şablonu parametresinden başvuruyu veya rvalue-Reference nitelik öğesini şeritler.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`Type`|Sınıf şablonu parametresi için eş anlamlı.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`RemoveReference`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** iç. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL::D euçlar ad alanı](microsoft-wrl-details-namespace.md)
