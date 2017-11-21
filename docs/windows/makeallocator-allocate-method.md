---
title: "MakeAllocator::Allocate yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::MakeAllocator::Allocate
dev_langs: C++
helpviewer_keywords: Allocate method
ms.assetid: a01997bc-4ff1-4ed0-9def-e4aaa15b0598
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 997386e42851c6d4e15aceac006b4e27eea35c44
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)