---
title: "EventTargetArray::AddTail yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
dev_langs:
- C++
helpviewer_keywords:
- AddTail method
ms.assetid: d0fafab9-049c-40e0-a40c-d126c9ee63e6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2ff008a60831ccce9a93bc3b4c4df8643db9c541
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="eventtargetarrayaddtail-method"></a>EventTargetArray::AddTail Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void AddTail(  
   _In_ IUnknown* element  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `element`  
 Eklenecek olay işleyicisi işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen olay işleyicisi olay işleyicileri iç dizisi sonuna ekler.  
  
 AddTail() yalnızca EventSource sınıfı tarafından dahili olarak kullanılmak üzere tasarlanmıştır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EventTargetArray sınıfı](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)