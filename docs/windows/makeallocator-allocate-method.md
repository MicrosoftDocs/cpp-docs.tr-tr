---
title: "MakeAllocator::Allocate yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
dev_langs:
- C++
helpviewer_keywords:
- Allocate method
ms.assetid: a01997bc-4ff1-4ed0-9def-e4aaa15b0598
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e93cd6b5b8b3489fc18e8b083c0fc59589ebd1d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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