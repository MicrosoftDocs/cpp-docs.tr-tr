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
ms.openlocfilehash: 0b8aa37f6ac12cad91fa02a2387c95911227319d
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466143"
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
|[CriticalSection::CriticalSection Oluşturucusu](../windows/criticalsection-criticalsection-constructor.md)|Mutex nesnesine benzer, ancak yalnızca tek bir işlem iş parçacığı tarafından kullanılan bir eşitleme nesnesi başlatır.|  
|[CriticalSection::~CriticalSection Yıkıcısı](../windows/criticalsection-tilde-criticalsection-destructor.md)|Başlatılmasını geri alır ve geçerli yok eder **CriticalSection** nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CriticalSection::TryLock Metodu](../windows/criticalsection-trylock-method.md)|Engelleme olmadan kritik bir bölüm girin dener. Çağrı başarılı olursa, çağıran iş parçacığı, kritik bölüm sahipliğini alır.|  
|[CriticalSection::Lock Metodu](../windows/criticalsection-lock-method.md)|Belirtilen kritik bölüm Nesne sahipliği için bekler. Çağıran iş parçacığını sahipliği verildiğinde işlevi döndürür.|  
|[CriticalSection::IsValid Metodu](../windows/criticalsection-isvalid-method.md)|Geçerli kritik bölüm geçerli olup olmadığını belirtir.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CriticalSection::cs_ Veri Üyesi](../windows/criticalsection-cs-data-member.md)|Kritik bölüm veri üyesi bildirir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CriticalSection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)