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
ms.openlocfilehash: bcacfb8d5cd6d15cf9ca5f9f5bb8e937119dc863
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691580"
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

*RuntimeClassFlagsT*  
Bir veya daha fazla belirten bayraklar alanı [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırıcılar.

*ILst*  
Arabirim kimlikleri listesi.

*IsDelegateToClass*  
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