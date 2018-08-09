---
title: RuntimeClass::Release yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::Release
dev_langs:
- C++
helpviewer_keywords:
- Release method
ms.assetid: 0bd6f9e2-ad90-4de6-adef-a6286f458cb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 317fb846fa7c4f64545762b473233e87ca049173
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017701"
---
# <a name="runtimeclassrelease-method"></a>RuntimeClass::Release Yöntemi
Geçerli bir COM yayınında işlemi gerçekleştirir **RuntimeClass** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
STDMETHOD_(  
   ULONG,  
   Release  
)();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Başvuru sayısı sıfır olduğunda **RuntimeClass** nesnesi silinir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [RuntimeClass Sınıfı](../windows/runtimeclass-class.md)