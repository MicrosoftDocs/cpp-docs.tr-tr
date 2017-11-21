---
title: "SRWLock::LockShared yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
dev_langs: C++
helpviewer_keywords: LockShared method
ms.assetid: 9d826a5c-b6a2-4430-ac85-d5753cbca889
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ac2807f453b2cead5482c65f2c70665ebc7dfb98
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="srwlocklockshared-method"></a>SRWLock::LockShared Yöntemi
Paylaşılan modda SRWLock nesneyi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
SyncLockShared LockShared();  
  
static SyncLockShared LockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `lock`  
 SRWLock nesnesine işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 SRWLock nesne paylaşılan modda.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SRWLock sınıfı](../windows/srwlock-class.md)