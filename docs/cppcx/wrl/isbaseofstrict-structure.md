---
description: 'Daha fazla bilgi edinin: ıbaseofstrict yapısı'
title: IsBaseOfStrict Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
helpviewer_keywords:
- Microsoft::WRL::Details::IsBaseOfStrict structure
- Microsoft::WRL::Details::IsBaseOfStrict::value constant
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
ms.openlocfilehash: bcdab9c4b6b5a2ab108b59d3127c08b53589e16a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298961"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename Base, typename Derived>
struct IsBaseOfStrict;

template <typename Base>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>Parametreler

*Temel*<br/>
Temel tür.

*Türetilmiş*<br/>
Türetilmiş tür.

## <a name="remarks"></a>Açıklamalar

Bir türün diğerinin temeli olup olmadığını test eder.

İlk şablon, bir türün bir temel türden türetilip türetilmediğini test eder, bu, **`true`** veya anlamına gelebilir **`false`** . İkinci şablon bir türün kendisinden türetilip türetilmediğini test eder ve her zaman verir **`false`** .

## <a name="members"></a>Üyeler

### <a name="public-constants"></a>Genel sabitler

Ad                            | Açıklama
------------------------------- | --------------------------------------------------
[IsBaseOfStrict:: Value](#value) | Bir türün diğerinin temeli olup olmadığını gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IsBaseOfStrict`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** iç. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="isbaseofstrictvalue"></a><a name="value"></a> IsBaseOfStrict:: Value

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
static const bool value = __is_base_of(Base, Derived);
```

### <a name="remarks"></a>Açıklamalar

Bir türün diğerinin temeli olup olmadığını gösterir.

`value`**`true`** tür, `Base` türün temel bir sınıfı ise, `Derived` Aksi durumda **`false`** .
