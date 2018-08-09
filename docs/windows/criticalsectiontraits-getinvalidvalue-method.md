---
title: Criticalsectiontraits::getınvalidvalue metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- GetInvalidValue method
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 01efd9bf3941a5b19e1f0fe6c106d47f1b6e9fcf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642067"
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>CriticalSectionTraits::GetInvalidValue Metodu
Uzmanlaşmış bir **CriticalSection** şablon böylece şablonu her zaman geçerli değil.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
inline static Type GetInvalidValue();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Her zaman için geçersiz bir kritik bölüm bir işaretçi döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `Type` Değiştirici olarak tanımlanmış olan `typedef CRITICAL_SECTION* Type;`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CriticalSectionTraits Yapısı](../windows/criticalsectiontraits-structure.md)