---
title: WeakReference::DecrementStrongReference yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
dev_langs:
- C++
helpviewer_keywords:
- DecrementStrongReference method
ms.assetid: 97d70d9f-41b8-4f8d-a6fa-4137cc4f9029
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9a73608bd2faa8de2c5e23eff84290e7dd5fae11
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417195"
---
# <a name="weakreferencedecrementstrongreference-method"></a>WeakReference::DecrementStrongReference Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
ULONG DecrementStrongReference();
```

## <a name="remarks"></a>Açıklamalar

Güçlü Başvuru geçerli sayısını azaltır **WeakReference** nesne.

Güçlü Başvuru sayısı sıfır olduğunda, güçlü başvuru kümesine **nullptr**.

## <a name="return-value"></a>Dönüş Değeri

İndirildiği güçlü başvuru sayısı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[WeakReference sınıfı](../windows/weakreference-class1.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)