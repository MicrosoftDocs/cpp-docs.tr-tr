---
title: "SRWLock::TryLockExclusive yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
dev_langs:
- C++
helpviewer_keywords:
- TryLockExclusive method
ms.assetid: 661e8b19-3058-4511-8742-c9fbb90412c7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ebeaae465bd387d3939f9588be3c4a8e5eaf507b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="srwlocktrylockexclusive-method"></a>SRWLock::TryLockExclusive Yöntemi
Geçerli veya belirtilen SRWLock nesnesi özel kullanım modu SRWLock nesnesinde almaya çalışır. Çağrı başarılı olursa, çağıran iş parçacığı kilit aittir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
SyncLockExclusive TryLockExclusive();  
  
static SyncLockExclusive TryLockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `lock`  
 SRWLock nesnesine işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, özel kullanım modu ve çağıran iş parçacığı SRWLock nesnesinde kilit aittir. Aksi halde, bir SRWLock nesne durumu geçersiz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SRWLock Sınıfı](../windows/srwlock-class.md)