---
description: 'Daha fazla bilgi edinin: VerifyInterfaceHelper yapısı'
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
ms.openlocfilehash: a9b51eac55666d15b8362fc070d0feb731e9674d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135037"
---
# <a name="verifyinterfacehelper-structure"></a>VerifyInterfaceHelper Yapısı

Windows Çalışma Zamanı C++ Şablon kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <bool isWinRTInterface, typename I>
struct VerifyInterfaceHelper;

template <typename I>
struct VerifyInterfaceHelper<false, I>;
```

### <a name="parameters"></a>Parametreler

*Kaydedemiyorum*<br/>
Doğrulanacak bir arabirim.

*Iswınrtınterface*

## <a name="remarks"></a>Açıklamalar

Şablon parametresi tarafından belirtilen arabirimin belirli gereksinimleri karşıladığını doğrular.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                            | Açıklama
----------------------------------------------- | ---------------------------------------------------------------------------------------------------
[VerifyInterfaceHelper::Verify Metodu](#verify) | Geçerli şablon parametresi tarafından belirtilen arabirimin belirli gereksinimleri karşıladığını doğrular.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VerifyInterfaceHelper`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="verifyinterfacehelperverify"></a><a name="verify"></a> VerifyInterfaceHelper:: Verify

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
static void Verify();
```

### <a name="remarks"></a>Açıklamalar

Geçerli şablon parametresi tarafından belirtilen arabirimin belirli gereksinimleri karşıladığını doğrular.
