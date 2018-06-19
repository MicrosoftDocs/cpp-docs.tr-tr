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
ms.openlocfilehash: c3353df1a73821a2009aeba2367f1892b06aba5b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889853"
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
 [SyncLockT Sınıfı](../windows/synclockt-class.md)