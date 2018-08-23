---
title: ComPtrRefBase::operator IUnknown ** işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
dev_langs:
- C++
helpviewer_keywords:
- operator IUnknown** operator
ms.assetid: c2950abf-a7aa-480a-ba41-615703e7f931
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a1a5b91ce4ffdfd376e6fbc7fa704fc1ecc0dc45
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613022"
---
# <a name="comptrrefbaseoperator-iunknown-operator"></a>ComPtrRefBase::operator IUnknown** İşleci

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
operator IUnknown**() const;
```

## <a name="remarks"></a>Açıklamalar

Geçerli bıraktığı [ptr_](../windows/comptrrefbase-ptr-data-member.md) veri üyesi için bir işaretçi-için-a-işaretçi- `IUnknown` arabirimi.

Bir hata varsa yayıldığını geçerli **ComPtrRefBase** öğesinden türetilen değil `IUnknown`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[ComPtrRefBase Sınıfı](../windows/comptrrefbase-class.md)  
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)