---
title: "AsyncBase::TryTransitionToCompleted yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted
dev_langs: C++
helpviewer_keywords: TryTransitionToCompleted method
ms.assetid: 8d038e0a-47ec-4cfc-8aeb-6821282df67a
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aeecd31e25d55222e18e1aa95f41b70ce7f5f889
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasetrytransitiontocompleted-method"></a>AsyncBase::TryTransitionToCompleted Yöntemi
Geçerli zaman uyumsuz işlemi tamamlanıp tamamlanmadığını gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
bool TryTransitionToCompleted(  
   void  
);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`zaman uyumsuz işlemi tamamlandı Aksi takdirde `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)