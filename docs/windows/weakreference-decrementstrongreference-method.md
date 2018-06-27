---
title: WeakReference::DecrementStrongReference yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
dev_langs:
- C++
helpviewer_keywords:
- DecrementStrongReference method
ms.assetid: 97d70d9f-41b8-4f8d-a6fa-4137cc4f9029
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d5605670e05f91f9f1293c8bff0f4d74e458d25
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890342"
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
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)