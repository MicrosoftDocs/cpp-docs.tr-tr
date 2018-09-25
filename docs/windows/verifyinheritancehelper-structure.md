---
title: Verifyınheritancehelper yapısı | Microsoft Docs
ms.custom: ''
ms.date: 09/24/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInheritanceHelper structure
- Microsoft::WRL::Details::VerifyInheritanceHelper::Verify method
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6231345b837cae8f36e8441173300d804c0ea167
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169639"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename I,
   typename Base
>
struct VerifyInheritanceHelper;
template <
   typename I
>
struct VerifyInheritanceHelper<I, Nil>;
```

### <a name="parameters"></a>Parametreler

*I*<br/>
Bir tür.

*temel*<br/>
Başka bir tür.

## <a name="remarks"></a>Açıklamalar

Başka bir arabirimden türetilmiş bir arabirim olup olmadığını sınar.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                       | Açıklama
------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------
[Verifyınheritancehelper::Verify](#verify) | Geçerli şablon parametreler ile belirtilen iki arabirim test eder ve bir arabirimin diğer türetilip türetilmediğini belirler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VerifyInheritanceHelper`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="verify"></a>Verifyınheritancehelper::Verify

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
static void Verify();
```

### <a name="remarks"></a>Açıklamalar

Geçerli şablon parametreler ile belirtilen iki arabirim test eder ve bir arabirimin diğer türetilip türetilmediğini belirler.

Bir arabirim diğerinden türetilmiş değil, bir hata yayılır.
