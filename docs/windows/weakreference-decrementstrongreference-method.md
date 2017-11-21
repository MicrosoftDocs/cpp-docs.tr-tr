---
title: "WeakReference::DecrementStrongReference yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
dev_langs: C++
helpviewer_keywords: DecrementStrongReference method
ms.assetid: 97d70d9f-41b8-4f8d-a6fa-4137cc4f9029
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8526385764206b3bb72691fa0ed5232f8f6edf8d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="weakreferencedecrementstrongreference-method"></a>WeakReference::DecrementStrongReference Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
ULONG DecrementStrongReference();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Güçlü Başvuru azaltır geçerli WeakReference nesne sayısı.  
  
 Güçlü Başvuru sayısı sıfır olduğunda, güçlü başvuru kümesine `nullptr`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Azaltılan güçlü başvuru sayısı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[WeakReference sınıfı](../windows/weakreference-class1.md)  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)