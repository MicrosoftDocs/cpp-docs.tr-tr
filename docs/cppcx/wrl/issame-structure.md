---
title: IsSame Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsSame
- internal/Microsoft::WRL::Details::IsSame::value
helpviewer_keywords:
- Microsoft::WRL::Details::IsSame structure
- Microsoft::WRL::Details::IsSame::value constant
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
ms.openlocfilehash: 8c209d5a8d2a35f2643e90e5595d86f41519f30b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216563"
---
# <a name="issame-structure"></a>IsSame Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <typename T1, typename T2>
struct IsSame;

template <typename T1>
struct IsSame<T1, T1>;
```

### <a name="parameters"></a>Parametreler

*T1*<br/>
Bir tür.

*T2*<br/>
Başka bir tür.

## <a name="remarks"></a>Açıklamalar

Belirtilen bir türün, belirtilen başka bir türle aynı olup olmadığını test eder.

## <a name="members"></a>Üyeler

### <a name="public-constants"></a>Genel sabitler

Ad                    | Açıklama
----------------------- | --------------------------------------------------
[IsSame:: değer](#value) | Bir türün diğeri ile aynı olup olmadığını gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IsSame`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** iç. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="issamevalue"></a><a name="value"></a>IsSame:: değer

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
template <typename T1, typename T2>
struct IsSame
{
    static const bool value = false;
};

template <typename T1>
struct IsSame<T1, T1>
{
    static const bool value = true;
};
```

### <a name="remarks"></a>Açıklamalar

Bir türün diğeri ile aynı olup olmadığını gösterir.

`value`**`true`** şablon parametrelerinin aynı olması ve **`false`** şablon parametrelerinin farklı olması durumunda.
