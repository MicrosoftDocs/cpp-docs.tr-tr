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
ms.openlocfilehash: ee338d4e90f94ed7cb7f9158235c66b72e9f2e52
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464752"
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
 `Cancel()` bir varsayılan uygulamasıdır `IAsyncInfo::Cancel`, ve hiçbir asıl işi yapar. Zaman uyumsuz bir işlem gerçekten iptal etmek için geçersiz kılma `OnCancel()` saf sanal yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)