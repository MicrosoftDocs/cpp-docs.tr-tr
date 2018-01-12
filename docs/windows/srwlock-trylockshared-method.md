---
title: "SRWLock::TryLockShared yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
dev_langs: C++
helpviewer_keywords: TryLockShared method
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c36657b5c732055260dc77471e109961a66c144
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="srwlocktrylockshared-method"></a>SRWLock::TryLockShared Yöntemi
SRWLock nesne geçerli veya belirtilen SRWLock nesnesi paylaşılan modda almaya çalışır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW SyncLockShared TryLockShared();  
WRL_NOTHROW static SyncLockShared TryLockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `lock`  
 SRWLock nesnesine işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, paylaşılan modda ve çağıran iş parçacığı SRWLock nesnesinde kilit aittir. Aksi halde, bir SRWLock nesne durumu geçersiz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SRWLock Sınıfı](../windows/srwlock-class.md)