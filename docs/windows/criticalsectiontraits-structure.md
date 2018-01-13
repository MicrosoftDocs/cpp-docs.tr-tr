---
title: "CriticalSectionTraits yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
dev_langs: C++
helpviewer_keywords: CriticalSectionTraits structure
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c24d8dea31a87094329276af3ebfaf9f06136adc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits Yapısı
Geçersiz bir kritik bölüm veya önemli bir bölümü serbest bırakmak için bir işlev desteklemek için bir CriticalSection nesnesi uzmanlaşmış.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CriticalSectionTraits;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`Type`|A `typedef` , kritik bir bölüm için bir işaretçi tanımlar. `Type`olarak tanımlanan `typedef CRITICAL_SECTION* Type;`.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CriticalSectionTraits::GetInvalidValue Metodu](../windows/criticalsectiontraits-getinvalidvalue-method.md)|Böylece şablon her zaman geçersiz CriticalSection şablon uzmanlaşmış.|  
|[CriticalSectionTraits::Unlock Metodu](../windows/criticalsectiontraits-unlock-method.md)|Böylece belirtilen kritik bölüm nesnenin sahipliğini serbest destekleyen bir CriticalSection şablonu uzmanlaşmış.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CriticalSectionTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::HandleTraits Ad Alanı](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)