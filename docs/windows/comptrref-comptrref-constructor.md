---
title: ComPtrRef::ComPtrRef Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef, constructor
ms.assetid: ce2d2533-fef6-4b2d-b088-6f3db01df5a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 621f852728cb40ea88a916b37147c28d8bb0db38
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644468"
---
# <a name="comptrrefcomptrref-constructor"></a>ComPtrRef::ComPtrRef Oluşturucusu
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
ComPtrRef(  
   _In_opt_ T* ptr  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *ptr*  
 Temeldeki değeri başka bir **ComPtrRef** nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Yeni bir örneğini başlatır **ComPtrRef** belirtilen işaretçisinden sınıfa **ComPtrRef** nesne.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtrRef sınıfı](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)