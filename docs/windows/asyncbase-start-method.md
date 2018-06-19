---
title: AsyncBase::Start yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0acc6f62530daf641a2e4d568ed511d6fd831c20
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860924"
---
# <a name="asyncbasestart-method"></a>AsyncBase::Start Yöntemi
Zaman uyumsuz işlemi başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   Start  
)(void);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlemi başlatır veya zaten varsa S_OK başlatıldı; Aksi takdirde E_ILLEGAL_STATE_CHANGE.  
  
## <a name="remarks"></a>Açıklamalar  
 Start() IAsyncInfo::Start varsayılan uygulamasıdır ve hiçbir asıl işi yapar. Zaman uyumsuz bir işlem gerçekten başlatmak için OnStart() saf sanal yöntemini geçersiz kılın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)