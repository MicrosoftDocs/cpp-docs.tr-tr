---
title: Implementshelper yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
dev_langs:
- C++
helpviewer_keywords:
- ImplementsHelper structure
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4ff40e03bf464d4c6f434b491c8b48d2b797d72b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440543"
---
# <a name="implementshelper-structure"></a>ImplementsHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename RuntimeClassFlagsT,
   typename ILst,
   bool IsDelegateToClass
>
friend struct Details::ImplementsHelper;
```

### <a name="parameters"></a>Parametreler

*RuntimeClassFlagsT*<br/>
Bir veya daha fazla belirten bayraklar alanı [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırıcılar.

*ILst*<br/>
Arabirim kimlikleri listesi.

*IsDelegateToClass*<br/>
Belirtin **true** varsa geçerli örneğini `Implements` ilk arabirim kimliği taban sınıfıdır *ILst*; Aksi takdirde **false**.

## <a name="remarks"></a>Açıklamalar

Uygulama yardımcı [uygular](../windows/implements-structure.md) yapısı.

Bu şablon, arabirimin bir listeyi dikkatle inceler ve temel sınıflar ve etkinleştirmek gereken bilgileri ekler `QueryInterface`.

## <a name="members"></a>Üyeler

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ImplementsHelper`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)