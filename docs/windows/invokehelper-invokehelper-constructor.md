---
title: "Invokehelper::ınvokehelper Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
dev_langs: C++
helpviewer_keywords: InvokeHelper, constructor
ms.assetid: 0223c574-abc3-4fc0-99e6-38626ba79243
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e7016ce1c0a3e9c4a327f5db66903461e6748176
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="invokehelperinvokehelper-constructor"></a>InvokeHelper::InvokeHelper Oluşturucusu
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
explicit InvokeHelper(  
   TCallback callback  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `callback`  
 Olay işleyicisi.  
  
## <a name="remarks"></a>Açıklamalar  
 Invokehelper sınıfının yeni bir örneğini başlatır.  
  
 `TCallback` Şablon parametresi olay işleyicisi türünü belirtir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Invokehelper yapısı](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)