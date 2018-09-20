---
title: ModuleBase::DecrementObjectCount yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount
dev_langs:
- C++
helpviewer_keywords:
- DecrementObjectCount method
ms.assetid: a016fb07-a36e-40cd-bc7b-8f6e85e256e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d90e0560ee5aa7036947e0d81f2d608b5a68bf75
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375929"
---
# <a name="modulebasedecrementobjectcount-method"></a>ModuleBase::DecrementObjectCount Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
virtual long DecrementObjectCount() = 0;
```

## <a name="return-value"></a>Dönüş Değeri

Azaltma işleminden önce sayısı.

## <a name="remarks"></a>Açıklamalar

Uygulandığında, azaltır nesne sayısını modülü tarafından izlenir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[ModuleBase Sınıfı](../windows/modulebase-class.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)