---
title: "AsyncBase::Cancel yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::Cancel
dev_langs: C++
helpviewer_keywords: Cancel method
ms.assetid: 8bfebc63-3848-4629-bc89-aa538ed7e7ad
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b6215c871da92087a7555bfb5a97f48d60223de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbasecancel-method"></a>AsyncBase::Cancel Yöntemi
Zaman uyumsuz bir işlem iptal eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   Cancel  
)(void);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Varsayılan olarak, her zaman S_OK döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Cancel() IAsyncInfo::Cancel varsayılan uygulamasıdır ve hiçbir asıl işi yapar. Zaman uyumsuz bir işlem gerçekten iptal etmek OnCancel() saf sanal yöntemini geçersiz kılın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase sınıfı](../windows/asyncbase-class.md)