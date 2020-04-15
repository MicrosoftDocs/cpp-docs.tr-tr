---
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
ms.openlocfilehash: 71db5a1b52a7d7d5471c15591fb34d954b465d07
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371362"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename Base, typename Derived>
struct IsBaseOfStrict;

template <typename Base>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>Parametreler

*Temel*<br/>
Temel türü.

*Türetilmiş*<br/>
Türetilmiş türü.

## <a name="remarks"></a>Açıklamalar

Bir türün diğerinin temeli olup olmadığını sınar.

İlk şablon, bir türün **doğru** veya **yanlış**verebilecek bir taban türünden türetilip türetilmediğini sınar. İkinci şablon, bir türün kendisinden türetilip türetilip türetilenin her zaman **yanlış**verir sınar.

## <a name="members"></a>Üyeler

### <a name="public-constants"></a>Genel Sabitler

Adı                            | Açıklama
------------------------------- | --------------------------------------------------
[IsBaseOfStrict::değer](#value) | Bir türün diğerinin temeli olup olmadığını gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IsBaseOfStrict`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** internal.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="isbaseofstrictvalue"></a><a name="value"></a>IsBaseOfStrict::değer

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
static const bool value = __is_base_of(Base, Derived);
```

### <a name="remarks"></a>Açıklamalar

Bir türün diğerinin temeli olup olmadığını gösterir.

`value`türü **true** `Base` türünün `Derived`bir taban sınıf ise doğrudur , aksi takdirde **yanlıştır**.
