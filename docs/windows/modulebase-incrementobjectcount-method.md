---
title: "Modulebase::ıncrementobjectcount yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
dev_langs:
- C++
helpviewer_keywords:
- IncrementObjectCount method
ms.assetid: 2d70b472-684c-4bb7-8bab-09505cfcaf28
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 773f909e6dad4aae1933db355510443846646df0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="modulebaseincrementobjectcount-method"></a>ModuleBase::IncrementObjectCount Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
virtual long IncrementObjectCount() = 0;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Artırma işleminden önce sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulandığında modül tarafından izlenen nesne sayısını artırır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ModuleBase sınıfı](../windows/modulebase-class.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)