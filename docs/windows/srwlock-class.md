---
title: "SRWLock sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::SRWLock
dev_langs: C++
helpviewer_keywords: SRWLock class
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b6721620490a00da0b9c8fa039be0379f4d7dd1b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="srwlock-class"></a>SRWLock Sınıfı
Bir ince Okuyucu/Yazıcı kilidi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class SRWLock;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir ince Okuyucu/Yazıcı kilit bir nesneye veya kaynak iş parçacıkları arasında erişimi eşitlemek için kullanılır. Daha fazla bilgi için bkz: [eşitleme işlevleri](http://msdn.microsoft.com/en-us/9b6359c2-0113-49b6-83d0-316ad95aba1b).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|||  
|-|-|  
|**SyncLockExclusive**|Eş anlamlı SRWLock nesnenin özel modda alınır.|  
|**SyncLockShared**|Paylaşılan modda alınan SRWLock nesne için eş anlamlı.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SRWLock::SRWLock Oluşturucusu](../windows/srwlock-srwlock-constructor.md)|SRWLock sınıfı yeni bir örneğini başlatır.|  
|[SRWLock:: ~ SRWLock yok Edicisi](../windows/srwlock-tilde-srwlock-destructor.md)|SRWLock sınıfı örneği deinitializes.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SRWLock::LockExclusive yöntemi](../windows/srwlock-lockexclusive-method.md)|Özel modda SRWLock nesneyi alır.|  
|[SRWLock::LockShared yöntemi](../windows/srwlock-lockshared-method.md)|Paylaşılan modda SRWLock nesneyi alır.|  
|[SRWLock::TryLockExclusive yöntemi](../windows/srwlock-trylockexclusive-method.md)|Geçerli veya belirtilen SRWLock nesnesi özel kullanım modu SRWLock nesnesinde almaya çalışır.|  
|[SRWLock::TryLockShared yöntemi](../windows/srwlock-trylockshared-method.md)|SRWLock nesne geçerli veya belirtilen SRWLock nesnesi paylaşılan modda almaya çalışır.|  
  
### <a name="protected-data-member"></a>Korumalı veri üyesi  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SRWLock::SRWLock_ veri üyesi](../windows/srwlock-srwlock-data-member.md)|Geçerli SRWLock nesnesi için temel alınan kilidi değişken içeriyor.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `SRWLock`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: Wrappers Namespace](../windows/microsoft-wrl-wrappers-namespace.md)