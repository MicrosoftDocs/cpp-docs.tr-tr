---
title: RemoveReference Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RemoveReference
helpviewer_keywords:
- RemoveReference structure
ms.assetid: 43ff91bb-815a-440e-b9fb-7dcbb7c863af
ms.openlocfilehash: fcb4d132198fff8dd6e2d55011f0c3a174b73f40
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613700"
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

Belirtilen sınıf şablonu parametre başvurusunu veya rvalue başvurusunu nitelik kaldırır.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`Type`|Sınıf şablon parametresi için eş anlamlıdır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`RemoveReference`

## <a name="requirements"></a>Gereksinimler

**Başlık:** internal.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)