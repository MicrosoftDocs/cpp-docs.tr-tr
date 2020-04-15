---
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
ms.openlocfilehash: 3650cfb70ffc12572b3965534eff4e1f2ecb2cf5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374227"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename I, typename Base>
struct VerifyInheritanceHelper;

template <typename I>
struct VerifyInheritanceHelper<I, Nil>;
```

### <a name="parameters"></a>Parametreler

*Ⅰ*<br/>
Bir tür.

*Temel*<br/>
Başka bir tür.

## <a name="remarks"></a>Açıklamalar

Bir arabirimin başka bir arabirimden türetilip türetilenin test edilir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                       | Açıklama
------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------
[VerifyInheritanceHelper::Doğrula](#verify) | Geçerli şablon parametreleri tarafından belirtilen iki arabirimi sınar ve bir arabirimin diğerinden türetilip türetilip türetilemeyeceğini belirler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VerifyInheritanceHelper`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** implements.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="verifyinheritancehelperverify"></a><a name="verify"></a>VerifyInheritanceHelper::Doğrula

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
static void Verify();
```

### <a name="remarks"></a>Açıklamalar

Geçerli şablon parametreleri tarafından belirtilen iki arabirimi sınar ve bir arabirimin diğerinden türetilip türetilip türetilemeyeceğini belirler.

Bir arabirim diğerinden türetilmiş değilse bir hata yayımlanır.
