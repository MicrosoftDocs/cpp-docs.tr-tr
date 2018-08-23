---
title: Verifyınheritancehelper::Verify yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: 3360082b-81ad-4191-9ec3-b4372f7207d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cfcbb57694fc18944d199c1d4c74d8c74a335783
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599121"
---
# <a name="verifyinheritancehelperverify-method"></a>VerifyInheritanceHelper::Verify Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
static void Verify();
```

## <a name="remarks"></a>Açıklamalar

Geçerli şablon parametreler ile belirtilen iki arabirim test eder ve bir arabirimin diğer türetilip türetilmediğini belirler.

Bir arabirim diğerinden türetilmiş değil, bir hata yayılır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[VerifyInheritanceHelper Yapısı](../windows/verifyinheritancehelper-structure.md)  
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)