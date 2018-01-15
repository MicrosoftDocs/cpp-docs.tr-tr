---
title: "ClassFactory::LockServer yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::ClassFactory::LockServer
dev_langs: C++
helpviewer_keywords: LockServer method
ms.assetid: 8d859815-956d-4f81-a5af-7cdee7e945de
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5f646f198d884e677b622a312cfdb6187802e1c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 `true`izlenen nesne sayısını artırmak için. `false`izlenen nesne sayısını düşürmek için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde E_FAIL.  
  
## <a name="remarks"></a>Açıklamalar  
 ClassFactory temel örneği nesneleri izler [Modülü](../windows/module-class.md) sınıfı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClassFactory Sınıfı](../windows/classfactory-class.md)