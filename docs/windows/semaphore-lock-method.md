---
title: "Semaphore::Lock yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
dev_langs: C++
helpviewer_keywords: Lock method
ms.assetid: 0eef6ede-dc7d-4f09-a6c8-2f7d39d65bfa
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1a4f931333c4dfe949678cc4bb6bf90b6dec0e85
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
[Semafor sınıfı](../windows/semaphore-class.md)
 