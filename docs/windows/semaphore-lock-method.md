---
title: Semaphore::Lock yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 0eef6ede-dc7d-4f09-a6c8-2f7d39d65bfa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80b4db212236da6c9fb320ff5a5e04f4e9f4a4c6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892481"
---
# <a name="semaphorelock-method"></a>Semaphore::Lock Yöntemi
Geçerli nesne ya da belirtilen tanıtıcı ile ilişkili semafor nesne kadar bekler ve iş durumundaki ya da belirtilen zaman aşımı aralığı geçti.  
  
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
  
#### <a name="parameters"></a>Parametreler  
 `milliseconds`  
 Milisaniye cinsinden zaman aşımı aralığı. Sonsuza kadar bekler SONSUZ varsayılan değerdir.  
  
 `h`  
 Semafor nesnesi için bir tanıtıcı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir Details::SyncLockWithStatusT\<HandleTraits::SemaphoreTraits >  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Semafor Sınıfı](../windows/semaphore-class.md)
 