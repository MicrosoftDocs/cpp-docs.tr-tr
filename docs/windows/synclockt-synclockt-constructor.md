---
title: "SyncLockT::SyncLockT Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
dev_langs: C++
helpviewer_keywords: SyncLockT, constructor
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fb7e1f9715f84a272e6bdb1029439f9310a65428
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="synclocktsynclockt-constructor"></a>SyncLockT::SyncLockT Oluşturucusu
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
SyncLockT(  
   _Inout_ SyncLockT&& other  
);  
  
explicit SyncLockT(  
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `other`  
 Bir rvalue-başka bir SyncLockT nesnesine başvuru.  
  
 `sync`  
 SyncLockWithStatusT başka bir nesneye başvuru.  
  
## <a name="remarks"></a>Açıklamalar  
 SyncLockT sınıfı yeni bir örneğini başlatır.  
  
 İlk Oluşturucu parametresi tarafından belirtilen başka bir SyncLockT nesne geçerli SyncLockT nesnesinden başlatır `other`ve diğer SyncLockT Nesne geçersiz kılar. İkinci oluşturucu olan `protected`ve geçersiz bir durum için geçerli SyncLockT nesnesini başlatır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SyncLockT sınıfı](../windows/synclockt-class.md)