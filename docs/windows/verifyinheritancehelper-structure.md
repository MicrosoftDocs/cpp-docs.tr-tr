---
title: Verifyınheritancehelper yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
dev_langs:
- C++
helpviewer_keywords:
- VerifyInheritanceHelper structure
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6a7b101091cefcdca65518c2a62bd274f7af4607
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610261"
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

*I*  
Bir tür.

*temel*  
Başka bir tür.

## <a name="remarks"></a>Açıklamalar

Başka bir arabirimden türetilmiş bir arabirim olup olmadığını sınar.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[VerifyInheritanceHelper::Verify Metodu](../windows/verifyinheritancehelper-verify-method.md)|Geçerli şablon parametreler ile belirtilen iki arabirim test eder ve bir arabirimin diğer türetilip türetilmediğini belirler.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VerifyInheritanceHelper`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)