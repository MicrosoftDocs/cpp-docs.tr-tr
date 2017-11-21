---
title: "CriticalSectionTraits::Unlock yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs: C++
helpviewer_keywords: Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 078ec4a1fa1af6c4660ff1171ab1b671ee9872f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [CriticalSectionTraits yapısı](../windows/criticalsectiontraits-structure.md)