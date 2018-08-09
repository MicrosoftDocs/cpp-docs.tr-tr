---
title: Weakreference::ıncrementstrongreference yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::IncrementStrongReference
dev_langs:
- C++
helpviewer_keywords:
- IncrementStrongReference method
ms.assetid: d0232426-a8cb-48b4-99d4-165de2d66cb9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 764a47fe03a2ad9f4e4d3d64a5627acc9c72d1b5
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018877"
---
# <a name="weakreferenceincrementstrongreference-method"></a>WeakReference::IncrementStrongReference Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
ULONG IncrementStrongReference();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Artan güçlü başvuru sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli güçlü başvuru sayısını artırır **WeakReference** nesne.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WeakReference sınıfı](../windows/weakreference-class1.md)  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)