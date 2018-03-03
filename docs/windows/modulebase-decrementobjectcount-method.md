---
title: "ModuleBase::DecrementObjectCount yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount
dev_langs:
- C++
helpviewer_keywords:
- DecrementObjectCount method
ms.assetid: a016fb07-a36e-40cd-bc7b-8f6e85e256e7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2a8679c82c3ea699c5b3842ca969f75cd5af9d68
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="modulebasedecrementobjectcount-method"></a>ModuleBase::DecrementObjectCount Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
virtual long DecrementObjectCount() = 0;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Azaltma işlemi önce sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulandığında, azaltır nesnelerin sayısı modül tarafından izlenir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ModuleBase sınıfı](../windows/modulebase-class.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)