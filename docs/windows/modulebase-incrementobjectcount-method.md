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
ms.openlocfilehash: f226018d1c3cae6dd3dbab34537d7ada50140a92
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610298"
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

[ModuleBase Sınıfı](../windows/modulebase-class.md)  
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)