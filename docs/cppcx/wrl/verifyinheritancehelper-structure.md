---
description: 'Daha fazla bilgi edinin: VerifyInheritanceHelper yapısı'
title: VerifyInheritanceHelper Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInheritanceHelper structure
- Microsoft::WRL::Details::VerifyInheritanceHelper::Verify method
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
ms.openlocfilehash: 672455482a2d21cb695124cad31740b6325c377d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135050"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename I, typename Base>
struct VerifyInheritanceHelper;

template <typename I>
struct VerifyInheritanceHelper<I, Nil>;
```

### <a name="parameters"></a>Parametreler

*Kaydedemiyorum*<br/>
Bir tür.

*Temel*<br/>
Başka bir tür.

## <a name="remarks"></a>Açıklamalar

Bir arabirimin başka bir arabirimden türetilip türetilmediğini sınar.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                       | Açıklama
------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------
[VerifyInheritanceHelper:: Verify](#verify) | Geçerli şablon parametreleri tarafından belirtilen iki arabirimi sınar ve bir arabirimin diğerine mi türetilemeyeceğini belirler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VerifyInheritanceHelper`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="verifyinheritancehelperverify"></a><a name="verify"></a> VerifyInheritanceHelper:: Verify

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
static void Verify();
```

### <a name="remarks"></a>Açıklamalar

Geçerli şablon parametreleri tarafından belirtilen iki arabirimi sınar ve bir arabirimin diğerine mi türetilemeyeceğini belirler.

Bir arabirim diğerine türetilmediği takdirde bir hata yayınlanır.
