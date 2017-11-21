---
title: "CriticalSection sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::CriticalSection
dev_langs: C++
helpviewer_keywords: CriticalSection class
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 89587f87bd71d2688bba2c128d28c01212b50b71
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[CriticalSection:: ~ CriticalSection yok Edicisi](../windows/criticalsection-tilde-criticalsection-destructor.md)|Deinitializes ve geçerli CriticalSection nesnesini yok eder.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CriticalSection::TryLock yöntemi](../windows/criticalsection-trylock-method.md)|Önemli bir bölümü engellenmeden girmek çalışır. Çağrı başarılı olursa, çağıran iş parçacığı kritik bölümünün aittir.|  
|[CriticalSection::Lock yöntemi](../windows/criticalsection-lock-method.md)|Belirtilen kritik bölüm nesnenin sahipliğini bekler. Çağıran iş parçacığı sahipliği verildiğinde işlevi döndürür.|  
|[Criticalsection::IsValid yöntemi](../windows/criticalsection-isvalid-method.md)|Geçerli kritik bölüm geçerli olup olmadığını gösterir.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CriticalSection::cs_ veri üyesi](../windows/criticalsection-cs-data-member.md)|Bir kritik bölüm veri üyesi bildirir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CriticalSection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: Wrappers Namespace](../windows/microsoft-wrl-wrappers-namespace.md)