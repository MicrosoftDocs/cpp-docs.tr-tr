---
title: "Criticalsectiontraits::getınvalidvalue yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- GetInvalidValue method
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 55bf0dedc286ed5dac8f48c7e8a2d43aa7741eff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>CriticalSectionTraits::GetInvalidValue Metodu
Böylece şablon her zaman geçersiz CriticalSection şablon uzmanlaşmış.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline static Type GetInvalidValue();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Her zaman bir işaretçi geçersiz bir kritik bölümüne döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 *Türü* değiştirici olarak tanımlanır `typedef CRITICAL_SECTION* Type;`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CriticalSectionTraits Yapısı](../windows/criticalsectiontraits-structure.md)