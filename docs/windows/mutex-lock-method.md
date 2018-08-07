---
title: Mutex::Lock yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 61d95072-b690-441e-a080-0bf94a733141
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c96ef497331fecf8125c51a7b8bd669ec758927
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603530"
---
# <a name="mutexlock-method"></a>Mutex::Lock Yöntemi
Geçerli nesne kadar bekler veya **Mutex** belirtilen tanıtıcısı, mutex veya belirtilen zaman aşımı aralığı geçtikten yayınlar ilişkili nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
SyncLock Lock(  
   DWORD milliseconds = INFINITE  
);  
  
static SyncLock Lock(  
   HANDLE h,  
   DWORD milliseconds = INFINITE  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *Milisaniye*  
 Milisaniye cinsinden zaman aşımı aralığı. Varsayılan değer süresiz olarak bekler sonsuzdur.  
  
 *h*  
 Tanıtıcısını bir **Mutex** nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Mutex sınıfı](../windows/mutex-class1.md)