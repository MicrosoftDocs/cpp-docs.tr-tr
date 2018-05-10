---
title: SRWLock sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock
dev_langs:
- C++
helpviewer_keywords:
- SRWLock class
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ec31b1469f437ff2776ed9da52fbcd7557fca8e2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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
|[SRWLock::~SRWLock Yıkıcısı](../windows/srwlock-tilde-srwlock-destructor.md)|SRWLock sınıfı örneği deinitializes.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SRWLock::LockExclusive Metodu](../windows/srwlock-lockexclusive-method.md)|Özel modda SRWLock nesneyi alır.|  
|[SRWLock::LockShared Metodu](../windows/srwlock-lockshared-method.md)|Paylaşılan modda SRWLock nesneyi alır.|  
|[SRWLock::TryLockExclusive Metodu](../windows/srwlock-trylockexclusive-method.md)|Geçerli veya belirtilen SRWLock nesnesi özel kullanım modu SRWLock nesnesinde almaya çalışır.|  
|[SRWLock::TryLockShared Metodu](../windows/srwlock-trylockshared-method.md)|SRWLock nesne geçerli veya belirtilen SRWLock nesnesi paylaşılan modda almaya çalışır.|  
  
### <a name="protected-data-member"></a>Korumalı veri üyesi  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SRWLock::SRWLock_ Veri Üyesi](../windows/srwlock-srwlock-data-member.md)|Geçerli SRWLock nesnesi için temel alınan kilidi değişken içeriyor.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `SRWLock`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)