---
title: VerifyInterfaceHelper Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInterfaceHelper structure
- Microsoft::WRL::Details::VerifyInterfaceHelper::Verify method
ms.assetid: ea95b641-199a-4fdf-964b-186b40cb3ba7
ms.openlocfilehash: 09c2cc7e08e2dc0e8df42c64d285c37627c5925a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374243"
---
# <a name="verifyinterfacehelper-structure"></a>VerifyInterfaceHelper Yapısı

Windows Runtime C++ Şablon Kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <bool isWinRTInterface, typename I>
struct VerifyInterfaceHelper;

template <typename I>
struct VerifyInterfaceHelper<false, I>;
```

### <a name="parameters"></a>Parametreler

*Ⅰ*<br/>
Doğrulamak için bir arayüz.

*isWinRTInterface*

## <a name="remarks"></a>Açıklamalar

Şablon parametresi tarafından belirtilen arabirimin belirli gereksinimleri karşıladığını doğrular.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                            | Açıklama
----------------------------------------------- | ---------------------------------------------------------------------------------------------------
[VerifyInterfaceHelper::Verify Metodu](#verify) | Geçerli şablon parametresi tarafından belirtilen arabirimin belirli gereksinimleri karşıladığını doğrular.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VerifyInterfaceHelper`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** implements.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="verifyinterfacehelperverify"></a><a name="verify"></a>VerifyInterfaceHelper::Doğrula

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
static void Verify();
```

### <a name="remarks"></a>Açıklamalar

Geçerli şablon parametresi tarafından belirtilen arabirimin belirli gereksinimleri karşıladığını doğrular.
