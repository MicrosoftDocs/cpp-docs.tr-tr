---
title: ComPtrRef::ReleaseAndGetAddressOf yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 004aac42-e135-41ce-8d1d-4c5969d55004
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 03f709feddb1c0e9c82cf80a4bd5f24e531414d3
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611225"
---
# <a name="comptrrefreleaseandgetaddressof-method"></a>ComPtrRef::ReleaseAndGetAddressOf Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
InterfaceType** ReleaseAndGetAddressOf();
```

## <a name="return-value"></a>Dönüş Değeri

Sunulacağı arabirim işaretçisi tarafından silinen **ComPtrRef** nesne.

## <a name="remarks"></a>Açıklamalar

Geçerli siler **ComPtrRef** nesnesi ve bir işaretçi-için-a-işaretçi tarafından temsil arabirimi döndürür **ComPtrRef** nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[ComPtrRef Sınıfı](../windows/comptrref-class.md)  
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)