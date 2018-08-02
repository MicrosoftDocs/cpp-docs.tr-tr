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
ms.openlocfilehash: cf0d52769052a36c0b494d19204dd6c07f0b2404
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463391"
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>CriticalSectionTraits::GetInvalidValue Metodu
Uzmanlaşmış bir **CriticalSection** şablon böylece şablonu her zaman geçerli değil.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline static Type GetInvalidValue();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Her zaman için geçersiz bir kritik bölüm bir işaretçi döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 *Türü* değiştirici olarak tanımlanmış olan `typedef CRITICAL_SECTION* Type;`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CriticalSectionTraits Yapısı](../windows/criticalsectiontraits-structure.md)