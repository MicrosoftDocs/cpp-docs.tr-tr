---
title: "CriticalSection sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection class
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e2bf6e4728bac6622f9872ab939e084b14f49ae8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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