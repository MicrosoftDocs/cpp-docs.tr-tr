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
ms.openlocfilehash: 3252096216757c34e93933bcdd91f9da2c5bb14f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015975"
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
 [MakeAllocator sınıfı](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)