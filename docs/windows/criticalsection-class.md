---
title: CriticalSection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection class
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8b5eda8fb22f72bd1f50801f9993b9bd7a864d35
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="criticalsection-class"></a>CriticalSection Sınıfı
Kritik bölüm nesneyi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CriticalSection;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="constructor"></a>Oluşturucu  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CriticalSection::CriticalSection Oluşturucusu](../windows/criticalsection-criticalsection-constructor.md)|Mutex nesnesine benzer, ancak yalnızca tek bir işlem iş parçacığı tarafından kullanılan bir eşitleme nesnesini başlatır.|  
|[CriticalSection::~CriticalSection Yıkıcısı](../windows/criticalsection-tilde-criticalsection-destructor.md)|Deinitializes ve geçerli CriticalSection nesnesini yok eder.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CriticalSection::TryLock Metodu](../windows/criticalsection-trylock-method.md)|Önemli bir bölümü engellenmeden girmek çalışır. Çağrı başarılı olursa, çağıran iş parçacığı kritik bölümünün aittir.|  
|[CriticalSection::Lock Metodu](../windows/criticalsection-lock-method.md)|Belirtilen kritik bölüm nesnenin sahipliğini bekler. Çağıran iş parçacığı sahipliği verildiğinde işlevi döndürür.|  
|[CriticalSection::IsValid Metodu](../windows/criticalsection-isvalid-method.md)|Geçerli kritik bölüm geçerli olup olmadığını gösterir.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CriticalSection::cs_ Veri Üyesi](../windows/criticalsection-cs-data-member.md)|Bir kritik bölüm veri üyesi bildirir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CriticalSection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)