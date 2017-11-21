---
title: "SRWLock::LockExclusive yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
dev_langs: C++
helpviewer_keywords: LockExclusive method
ms.assetid: f361b672-fca6-45cc-a9b4-310cc0d23fdc
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bb389b0aee2e995981e3d4570d3609ecae0dcaa5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="srwlocklockexclusive-method"></a>SRWLock::LockExclusive Yöntemi
Özel modda SRWLock nesneyi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
SyncLockExclusive LockExclusive();  
  
static SyncLockExclusive LockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `lock`  
 SRWLock nesnesine işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 SRWLock nesne özel modda.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SRWLock sınıfı](../windows/srwlock-class.md)