---
title: "SyncLockWithStatusT::SyncLockWithStatusT Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
dev_langs: C++
helpviewer_keywords: SyncLockWithStatusT, constructor
ms.assetid: 5d2fb820-ae1b-495f-8084-ebb4fecc3104
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 00602992585e496a41a4ecea6d85ed798adac640
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="synclockwithstatustsynclockwithstatust-constructor"></a>SyncLockWithStatusT::SyncLockWithStatusT Oluşturucusu
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
SyncLockWithStatusT(  
   _Inout_ SyncLockWithStatusT&& other  
);  
  
explicit SyncLockWithStatusT(  
   typename SyncTraits::Type sync,  
   DWORD status  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `other`  
 Bir rvalue-başka bir SyncLockWithStatusT nesnesine başvuru.  
  
 `sync`  
 SyncLockWithStatusT başka bir nesneye başvuru.  
  
 `status`  
 Değeri [status_](../windows/synclockwithstatust-status-data-member.md) veri üyesi `other` parametresi veya `sync` parametresi.  
  
## <a name="remarks"></a>Açıklamalar  
 SyncLockWithStatusT sınıfı yeni bir örneğini başlatır.  
  
 İlk Oluşturucu parametresi tarafından belirtilen başka bir SyncLockWithStatusT geçerli SyncLockWithStatusT nesnesinden başlatır `other`ve diğer SyncLockWithStatusT Nesne geçersiz kılar. İkinci oluşturucu olan `protected`ve geçersiz bir durum için geçerli SyncLockWithStatusT nesnesini başlatır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SyncLockWithStatusT sınıfı](../windows/synclockwithstatust-class.md)   
 [SyncLockWithStatusT::GetStatus metodu](../windows/synclockwithstatust-getstatus-method.md)