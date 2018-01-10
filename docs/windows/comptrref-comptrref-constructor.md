---
title: "ComPtrRef::ComPtrRef Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef
dev_langs: C++
helpviewer_keywords: ComPtrRef, constructor
ms.assetid: ce2d2533-fef6-4b2d-b088-6f3db01df5a5
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1e5012af680722c07432b492c4ca1ead5dc44cc4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrrefcomptrref-constructor"></a>ComPtrRef::ComPtrRef Oluşturucusu
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
ComPtrRef(  
   _In_opt_ T* ptr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ptr`  
 Başka bir ComPtrRef nesnenin temel alınan değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen işaretçi ComPtrRef sınıfından başka bir ComPtrRef nesne için yeni bir örneğini başlatır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtrRef sınıfı](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)