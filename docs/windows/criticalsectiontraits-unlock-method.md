---
title: CriticalSectionTraits::Unlock yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2f66f185692c200ea459b88363143c0cc1af9d55
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466016"
---
# <a name="criticalsectiontraitsunlock-method"></a>CriticalSectionTraits::Unlock Yöntemi
Belirtilen kritik bölüm nesneyi serbest bırakma sahipliğini destekler böylece bir CriticalSection şablon uzmanlaşmış.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *cs*  
 Kritik bölüm nesnesine bir işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 *Türü* değiştirici olarak tanımlanmış olan `typedef CRITICAL_SECTION* Type;`.  
  
 Daha fazla bilgi için "LeaveCriticalSection işlevi" Windows API belgeleri "Eşitleme işlevleri" bölümünde.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CriticalSectionTraits Yapısı](../windows/criticalsectiontraits-structure.md)