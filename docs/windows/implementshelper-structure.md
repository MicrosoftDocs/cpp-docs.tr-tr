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
ms.openlocfilehash: 5a3a31125d8489551f1eec143013661bf385f29a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212451"
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

[Başvuru (Windows çalışma zamanı kitaplığı)](https://msdn.microsoft.com/00000000-0000-0000-0000-000000000000)  
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)