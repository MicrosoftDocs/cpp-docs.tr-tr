---
title: CriticalSectionTraits yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
dev_langs:
- C++
helpviewer_keywords:
- CriticalSectionTraits structure
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5534173d594b8fc09ceca8ec44a1c1223bc550b2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33870557"
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
|`Type`|A `typedef` , kritik bir bölüm için bir işaretçi tanımlar. `Type` olarak tanımlanan `typedef CRITICAL_SECTION* Type;`.|  
  
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