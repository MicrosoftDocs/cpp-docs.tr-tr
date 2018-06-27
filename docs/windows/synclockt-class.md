---
title: SyncLockT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT class
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e05a1be5d84db52573d3c3235936ecf82dde5894
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892858"
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