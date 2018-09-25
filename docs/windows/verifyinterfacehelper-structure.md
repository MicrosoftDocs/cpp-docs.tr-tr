---
title: Verifyınterfacehelper yapısı | Microsoft Docs
ms.custom: ''
ms.date: 09/24/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper::Verify
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInterfaceHelper structure
- Microsoft::WRL::Details::VerifyInterfaceHelper::Verify method
ms.assetid: ea95b641-199a-4fdf-964b-186b40cb3ba7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e7aa7d796fb30a30a100f5f914feec57909407e5
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169768"
---
# <a name="verifyinterfacehelper-structure"></a>VerifyInterfaceHelper Yapısı

Windows çalışma zamanı C++ Şablon kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   bool isWinRTInterface,
   typename I
>
struct VerifyInterfaceHelper;

template <
   typename I
>
struct VerifyInterfaceHelper<false, I>;
```

### <a name="parameters"></a>Parametreler

*I*<br/>
Doğrulamak için bir arabirim.

*isWinRTInterface*

## <a name="remarks"></a>Açıklamalar

Şablon parametresi tarafından belirtilen arabirim belirli gereksinimleri karşıladığını doğrular.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                            | Açıklama
----------------------------------------------- | ---------------------------------------------------------------------------------------------------
[VerifyInterfaceHelper::Verify Metodu](#verify) | Geçerli bir şablon parametresi tarafından belirtilen arabirim belirli gereksinimleri karşıladığını doğrular.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VerifyInterfaceHelper`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="verify"></a>Verifyınterfacehelper::Verify

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
static void Verify();
```

### <a name="remarks"></a>Açıklamalar

Geçerli bir şablon parametresi tarafından belirtilen arabirim belirli gereksinimleri karşıladığını doğrular.
