---
title: Invokehelper::ınvokehelper Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
dev_langs:
- C++
helpviewer_keywords:
- InvokeHelper, constructor
ms.assetid: 0223c574-abc3-4fc0-99e6-38626ba79243
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 75ad1b82d6d4a28db94ef00a234547091969722b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020033"
---
# <a name="invokehelperinvokehelper-constructor"></a>InvokeHelper::InvokeHelper Oluşturucusu
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
explicit InvokeHelper(  
   TCallback callback  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *geri çağırma*  
 Bir olay işleyicisi.  
  
## <a name="remarks"></a>Açıklamalar  
 Yeni bir örneğini başlatır **Invokehelper** sınıfı.  
  
 `TCallback` Şablon parametresi, olay işleyicisi türünü belirtir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Invokehelper yapısı](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)