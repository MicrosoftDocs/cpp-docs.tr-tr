---
title: "SyncLockT sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT class
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3f3a9794f7b00a2029f6706db3a846ba127a4d5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="synclockt-class"></a>SyncLockT Sınıfı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockT;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `SyncTraits`  
 Bir kaynak sahipliğini alabilir türü.  
  
## <a name="remarks"></a>Açıklamalar  
 Özel gerçekleştirebileceğiniz bir türü temsil eder veya bir kaynak sahipliğini paylaşılan.  
  
 SyncLockT sınıfı, örneğin, uygulamaya yardımcı olmak için kullanılan [SRWLock](../windows/srwlock-class.md) sınıfı.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SyncLockT::SyncLockT Oluşturucusu](../windows/synclockt-synclockt-constructor.md)|SyncLockT sınıfı yeni bir örneğini başlatır.|  
|[SyncLockT::~SyncLockT Yıkıcısı](../windows/synclockt-tilde-synclockt-destructor.md)|SyncLockT sınıfı örneği deinitializes.|  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SyncLockT::SyncLockT Oluşturucusu](../windows/synclockt-synclockt-constructor.md)|SyncLockT sınıfı yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SyncLockT::IsLocked Metodu](../windows/synclockt-islocked-method.md)|Geçerli SyncLockT nesne bir kaynağa sahip olup olmadığını gösterir; diğer bir deyişle, SyncLockT nesnesidir *kilitli*.|  
|[SyncLockT::Unlock Metodu](../windows/synclockt-unlock-method.md)|Varsa geçerli SyncLockT nesne tarafından tutulan kaynak denetimini serbest bırakır.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SyncLockT::sync_ Veri Üyesi](../windows/synclockt-sync-data-member.md)|SyncLockT sınıfı tarafından temsil edilen temel alınan kaynak tutar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `SyncLockT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::details Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)   
 [SRWLock Sınıfı](../windows/srwlock-class.md)