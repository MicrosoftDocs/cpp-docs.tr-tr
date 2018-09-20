---
title: ComPtrRef::operator void ** işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator void**
dev_langs:
- C++
helpviewer_keywords:
- operator void** operator
ms.assetid: f020045c-9de4-4392-8783-73f0fc0761c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 977e04b923a99cab3eb42544de99c4fcee974e82
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408875"
---
# <a name="comptrrefoperator-void-operator"></a>ComPtrRef::operator void\* \* işleci

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
operator void**() const;
```

## <a name="remarks"></a>Açıklamalar

Geçerli siler **ComPtrRef** nesne, işaretçi tarafından temsil arabirimine bıraktığı **ComPtrRef** nesnesi olarak bir işaretçiyi-için-işaretçi- **void**ve ardından cast işaretçiyi döndürür.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[ComPtrRef Sınıfı](../windows/comptrref-class.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)