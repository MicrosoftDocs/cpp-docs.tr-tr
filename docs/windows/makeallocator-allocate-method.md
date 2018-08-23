---
title: MakeAllocator::Allocate yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
dev_langs:
- C++
helpviewer_keywords:
- Allocate method
ms.assetid: a01997bc-4ff1-4ed0-9def-e4aaa15b0598
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4422dea0b0bfb07904d0c4defad8f33281a51bec
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609868"
---
# <a name="makeallocatorallocate-method"></a>MakeAllocator::Allocate Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
__forceinline void* Allocate();
```

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ayrılan bellek; işaretçisi Aksi takdirde, **nullptr**.

## <a name="remarks"></a>Açıklamalar

Bellek ayırır ve geçerli ilişkilendirir **MakeAllocator** nesne.

Ayrılan bellek boyutu geçerli belirtilen tür boyutudur **MakeAllocator** şablon parametresi.

Yalnızca geçersiz kılmak bir geliştiricinin ihtiyaç duyduğu **Allocate()** farklı bellek ayırma modeli uygulamak için yöntemi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[MakeAllocator Sınıfı](../windows/makeallocator-class.md)  
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)