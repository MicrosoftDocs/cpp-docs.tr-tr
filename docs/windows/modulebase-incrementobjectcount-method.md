---
title: Modulebase::ıncrementobjectcount yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
dev_langs:
- C++
helpviewer_keywords:
- IncrementObjectCount method
ms.assetid: 2d70b472-684c-4bb7-8bab-09505cfcaf28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b8ac3bcb256c4a54f3b967405e7f2c0699e715d1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377189"
---
# <a name="modulebaseincrementobjectcount-method"></a>ModuleBase::IncrementObjectCount Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
virtual long IncrementObjectCount() = 0;
```

## <a name="return-value"></a>Dönüş Değeri

Önce Artım işlemi sayısı.

## <a name="remarks"></a>Açıklamalar

Uygulandığında, modül tarafından izlenen nesne sayısını artırır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[ModuleBase Sınıfı](../windows/modulebase-class.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)