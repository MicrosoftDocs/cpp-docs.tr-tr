---
title: ClassFactory::LockServer yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory::LockServer
dev_langs:
- C++
helpviewer_keywords:
- LockServer method
ms.assetid: 8d859815-956d-4f81-a5af-7cdee7e945de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9e09a795688c7e2b31771126f9e4036ddfbd8e4f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="classfactorylockserver-method"></a>ClassFactory::LockServer Yöntemi
Arka plandaki sayısı geçerli ClassFactory nesne tarafından izlenen nesneleri artırır veya azaltır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   LockServer  
)(BOOL fLock);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fLock`  
 `true` izlenen nesne sayısını artırmak için. `false` izlenen nesne sayısını düşürmek için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde E_FAIL.  
  
## <a name="remarks"></a>Açıklamalar  
 ClassFactory temel örneği nesneleri izler [Modülü](../windows/module-class.md) sınıfı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClassFactory Sınıfı](../windows/classfactory-class.md)