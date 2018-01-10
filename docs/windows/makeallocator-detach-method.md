---
title: "MakeAllocator::Detach yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::MakeAllocator::Detach
dev_langs: C++
helpviewer_keywords: Detach method
ms.assetid: 78012634-2dda-4ea2-9ffe-40f105d2fe47
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d114f48a2d4da7916f6ee7439a92297360b8476e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="makeallocatordetach-method"></a>MakeAllocator::Detach Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__forceinline void Detach();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tarafından ayrılan bellek keser [ayırma](../windows/makeallocator-allocate-method.md) geçerli MakeAllocator nesnesinden yöntemi.  
  
 Detach() çağırırsanız, bellek ayırma yöntemi tarafından sağlanan silmek için sorumludur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MakeAllocator sınıfı](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)