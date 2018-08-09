---
title: SyncLockT::SyncLockT Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT, constructor
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ceaafd6230e6497ed2b7636ad5070141546cb8d6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648171"
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
  
### <a name="parameters"></a>Parametreler  
 *Diğer*  
 Diğer bir rvalue başvurusuna **SyncLockT** nesne.  
  
 *Eşitleme*  
 Başka bir başvuru `SyncLockWithStatusT` nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Yeni bir örneğini başlatır **SyncLockT** sınıfı.  
  
 İlk Oluşturucu geçerli başlatır **SyncLockT** başka bir nesne **SyncLockT** parametresi tarafından belirtilen nesne *diğer*ve ardından diğer geçersizkılar **SyncLockT** nesne. İkinci oluşturucu **korumalı**ve geçerli başlatır **SyncLockT** nesnesi için geçersiz bir durumda.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SyncLockT Sınıfı](../windows/synclockt-class.md)