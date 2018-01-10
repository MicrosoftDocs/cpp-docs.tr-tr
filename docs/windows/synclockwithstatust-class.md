---
title: "SyncLockWithStatusT sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
dev_langs: C++
helpviewer_keywords: SyncLockWithStatusT class
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b4b007acd6e6b9272a4fc7bb256d302cafeb75c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT Sınıfı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `SyncTraits`  
 Özel gerçekleştirebileceğiniz bir tür veya bir kaynak sahipliğini paylaşılan.  
  
## <a name="remarks"></a>Açıklamalar  
 Özel gerçekleştirebileceğiniz bir türü temsil eder veya bir kaynak sahipliğini paylaşılan.  
  
 SyncLockWithStatusT sınıfı uygulamak için kullanılan [Mutex](../windows/mutex-class1.md) ve [semafor](../windows/semaphore-class.md) sınıfları.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SyncLockWithStatusT::SyncLockWithStatusT Oluşturucusu](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|SyncLockWithStatusT sınıfı yeni bir örneğini başlatır.|  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SyncLockWithStatusT::SyncLockWithStatusT Oluşturucusu](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|SyncLockWithStatusT sınıfı yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SyncLockWithStatusT::GetStatus Metodu](../windows/synclockwithstatust-getstatus-method.md)|Geçerli SyncLockWithStatusT nesnesinin bekleme durumunu alır.|  
|[SyncLockWithStatusT::IsLocked Metodu](../windows/synclockwithstatust-islocked-method.md)|Geçerli SyncLockWithStatusT nesne bir kaynağa sahip olup olmadığını gösterir; diğer bir deyişle, SyncLockWithStatusT nesnesidir *kilitli*.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SyncLockWithStatusT::status_ Veri Üyesi](../windows/synclockwithstatust-status-data-member.md)|Arka plandaki sonucu üzerinde bir kilit işlemi sonra işlemi bekleyin ayrı tutma bir nesne geçerli SyncLockWithStatusT nesnesine bağlı.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `SyncLockT`  
  
 `SyncLockWithStatusT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::Details Ad Alanı](../windows/microsoft-wrl-wrappers-details-namespace.md)