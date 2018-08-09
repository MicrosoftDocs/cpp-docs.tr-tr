---
title: SRWLock::LockExclusive yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
dev_langs:
- C++
helpviewer_keywords:
- LockExclusive method
ms.assetid: f361b672-fca6-45cc-a9b4-310cc0d23fdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 922220c9406f02568299dc60960b04a9820a7e95
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010967"
---
# <a name="srwlocklockexclusive-method"></a>SRWLock::LockExclusive Yöntemi
Alması bir **SRWLock** özel modda nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SyncLockExclusive LockExclusive();  
  
static SyncLockExclusive LockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *lock*  
 İşaretçi bir **SRWLock** nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir **SRWLock** özel modda nesne.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SRWLock Sınıfı](../windows/srwlock-class.md)