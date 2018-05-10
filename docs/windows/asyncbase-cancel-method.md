---
title: AsyncBase::Cancel yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Cancel
dev_langs:
- C++
helpviewer_keywords:
- Cancel method
ms.assetid: 8bfebc63-3848-4629-bc89-aa538ed7e7ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0559f32315265a7db5543e8559097177c2a670fa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)