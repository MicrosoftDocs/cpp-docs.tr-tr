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
ms.openlocfilehash: d0e8d387dea7687ad61d85f975d58aa47489266d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="makeallocatorallocate-method"></a>MakeAllocator::Allocate Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__forceinline void* Allocate();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, ayrılmış bellek için; bir işaretçi Aksi takdirde `nullptr`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bellek ayırır ve geçerli MakeAllocator nesnesi ile ilişkilendirir.  
  
 Ayrılmış bellek boyutu geçerli MakeAllocator şablon parametresi tarafından belirtilen tür boyutudur.  
  
 Bir geliştirici farklı bellek ayırma modeli uygulamak için yalnızca Allocate() yöntemini geçersiz kılın gerekiyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MakeAllocator sınıfı](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)