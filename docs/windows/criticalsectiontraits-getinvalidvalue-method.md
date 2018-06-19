---
title: Criticalsectiontraits::getınvalidvalue yöntemi | Microsoft Docs
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
ms.openlocfilehash: d72c9dce0765029ee31e079315baec72afd16a46
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883153"
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