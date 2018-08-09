---
title: RuntimeClass::DecrementReference yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::DecrementReference
dev_langs:
- C++
ms.assetid: f5ecfeaa-2865-455b-9208-94a0685fd2c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a9577427ed5a63b99d372226f8e7416a21cb6b1e
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010866"
---
# <a name="runtimeclassdecrementreference-method"></a>RuntimeClass::DecrementReference Yöntemi
Başvuru için geçerli sayısını azaltır **RuntimeClass** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
ULONG DecrementReference();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [RuntimeClass Sınıfı](../windows/runtimeclass-class.md)