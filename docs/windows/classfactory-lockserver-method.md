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
ms.openlocfilehash: 654ef60c924a14e861971c651899c8baea0300ef
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462712"
---
# <a name="classfactorylockserver-method"></a>ClassFactory::LockServer Yöntemi
Artırır veya azaltır temel sayısını nesneleri geçerli tarafından izlenen **ClassFactory** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   LockServer  
)(BOOL fLock);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *fLock*  
 **doğru** izlenen nesne sayısını artırmak için. **false** izlenen nesnelerin sayısını azaltmak için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, E_FAIL.  
  
## <a name="remarks"></a>Açıklamalar  
 ClassFactory temel örneği nesneleri izler [Modülü](../windows/module-class.md) sınıfı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClassFactory Sınıfı](../windows/classfactory-class.md)