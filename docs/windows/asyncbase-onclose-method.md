---
title: AsyncBase::OnClose yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::OnClose
dev_langs:
- C++
helpviewer_keywords:
- OnClose method
ms.assetid: 96766450-c262-4611-8534-7d190b799142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3c1b888b9d3e3f3c80c3aff40f5fd545ece9cca6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650644"
---
# <a name="asyncbaseonclose-method"></a>AsyncBase::OnClose Yöntemi
Türetilen bir sınıfta geçersiz kılındığında, zaman uyumsuz bir işlem kapatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
virtual void OnClose(  
   void  
) = 0;  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase sınıfı](../windows/asyncbase-class.md)   
 [AsyncBase::Close Metodu](../windows/asyncbase-close-method.md)