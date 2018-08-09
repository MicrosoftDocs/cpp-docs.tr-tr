---
title: SRWLock::TryLockShared yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
dev_langs:
- C++
helpviewer_keywords:
- TryLockShared method
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e67ecd6d5b4968af94ff1a82ad8be24e5b816298
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014253"
---
# <a name="srwlocktrylockshared-method"></a>SRWLock::TryLockShared Yöntemi
Almaya çalışır bir **SRWLock** nesne için geçerli veya belirtilen paylaşılan modda **SRWLock** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
WRL_NOTHROW SyncLockShared TryLockShared();  
WRL_NOTHROW static SyncLockShared TryLockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *lock*  
 İşaretçi bir **SRWLock** nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, bir **SRWLock** paylaşılan modda ve çağıran iş parçacığını nesne kilidi sahipliğini alır. Aksi takdirde, bir **SRWLock** nesne durumu geçersiz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SRWLock Sınıfı](../windows/srwlock-class.md)