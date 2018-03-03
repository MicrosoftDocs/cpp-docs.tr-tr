---
title: "SyncLockWithStatusT::SyncLockWithStatusT Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT, constructor
ms.assetid: 5d2fb820-ae1b-495f-8084-ebb4fecc3104
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dc5be4a37182cb23b47a2511d2e7d5eb0ffa558a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [SyncLockWithStatusT::GetStatus Metodu](../windows/synclockwithstatust-getstatus-method.md)