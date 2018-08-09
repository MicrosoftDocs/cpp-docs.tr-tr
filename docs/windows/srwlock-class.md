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
ms.openlocfilehash: 58b537a29a042f2227f3c2c121a320532d52877c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016372"
---
# <a name="srwlock-class"></a>SRWLock Sınıfı
Bir ince Okuyucu/Yazıcı kilidi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
class SRWLock;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir ince Okuyucu/Yazıcı kilidi, bir nesneye veya kaynak iş parçacıkları arasında erişimi eşitlemek için kullanılır. Daha fazla bilgi için [eşitleme işlevleri](http://msdn.microsoft.com/9b6359c2-0113-49b6-83d0-316ad95aba1b).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel Typedefler  
  
|||  
|-|-|  
|`SyncLockExclusive`|İçin eş anlamlı bir **SRWLock** özel modda alınan nesne.|  
|`SyncLockShared`|İçin eş anlamlı bir **SRWLock** paylaşılan modda alınan nesne.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SRWLock::SRWLock Oluşturucusu](../windows/srwlock-srwlock-constructor.md)|Yeni bir örneğini başlatır **SRWLock** sınıfı.|  
|[SRWLock::~SRWLock Yıkıcısı](../windows/srwlock-tilde-srwlock-destructor.md)|Örneği başlatılmasını geri alır **SRWLock** sınıfı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SRWLock::LockExclusive Metodu](../windows/srwlock-lockexclusive-method.md)|Alması bir **SRWLock** özel modda nesne.|  
|[SRWLock::LockShared Metodu](../windows/srwlock-lockshared-method.md)|Alması bir **SRWLock** paylaşılan modda nesne.|  
|[SRWLock::TryLockExclusive Metodu](../windows/srwlock-trylockexclusive-method.md)|Almaya çalışır bir **SRWLock** nesne için geçerli veya belirtilen özel modda **SRWLock** nesne.|  
|[SRWLock::TryLockShared Metodu](../windows/srwlock-trylockshared-method.md)|Almaya çalışır bir **SRWLock** nesne için geçerli veya belirtilen paylaşılan modda **SRWLock** nesne.|  
  
### <a name="protected-data-member"></a>Korumalı veri üyesi  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SRWLock::SRWLock_ Veri Üyesi](../windows/srwlock-srwlock-data-member.md)|Temel alınan kilidi değişken için geçerli içeren **SRWLock** nesne.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `SRWLock`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)