---
title: "SyncLockT sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
dev_langs: C++
helpviewer_keywords: SyncLockT class
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 70e50f4ab18cdfddc3330e5c23e5808040c354bb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[SyncLockT:: ~ SyncLockT yok Edicisi](../windows/synclockt-tilde-synclockt-destructor.md)|SyncLockT sınıfı örneği deinitializes.|  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SyncLockT::SyncLockT Oluşturucusu](../windows/synclockt-synclockt-constructor.md)|SyncLockT sınıfı yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Synclockt::IsLocked yöntemi](../windows/synclockt-islocked-method.md)|Geçerli SyncLockT nesne bir kaynağa sahip olup olmadığını gösterir; diğer bir deyişle, SyncLockT nesnesidir *kilitli*.|  
|[SyncLockT::Unlock yöntemi](../windows/synclockt-unlock-method.md)|Varsa geçerli SyncLockT nesne tarafından tutulan kaynak denetimini serbest bırakır.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SyncLockT::sync_ veri üyesi](../windows/synclockt-sync-data-member.md)|SyncLockT sınıfı tarafından temsil edilen temel alınan kaynak tutar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `SyncLockT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::details Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)   
 [SRWLock sınıfı](../windows/srwlock-class.md)