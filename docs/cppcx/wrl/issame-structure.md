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
ms.openlocfilehash: fcaf33309521b44163022e0ffa9b1e03e53e2551
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371343"
---
# <a name="issame-structure"></a>IsSame Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

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

Belirtilen bir türün başka bir belirtilen türle aynı olup olmadığını sınar.

## <a name="members"></a>Üyeler

### <a name="public-constants"></a>Genel Sabitler

Adı                    | Açıklama
----------------------- | --------------------------------------------------
[IsSame::değer](#value) | Bir türün diğerinin aynı olup olmadığını gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IsSame`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** internal.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="issamevalue"></a><a name="value"></a>IsSame::değer

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

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

Bir türün diğerinin aynı olup olmadığını gösterir.

`value`şablon parametreleri aynıysa ve şablon parametreleri farklıysa **yanlış** ise **doğrudur.**
