---
title: "CriticalSectionTraits::Unlock yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f9880364c24b1e2e5889e9e9e2666683c2237f7f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsectiontraitsunlock-method"></a>CriticalSectionTraits::Unlock Yöntemi
Böylece belirtilen kritik bölüm nesnenin sahipliğini serbest destekleyen bir CriticalSection şablonu uzmanlaşmış.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cs`  
 Kritik bölüm nesnesine bir işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 *Türü* değiştirici olarak tanımlanır `typedef CRITICAL_SECTION* Type;`.  
  
 Daha fazla bilgi için bkz: Windows API belgelerine "Eşitleme işlevleri" bölümündeki "LeaveCriticalSection işlev".  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CriticalSectionTraits Yapısı](../windows/criticalsectiontraits-structure.md)