---
title: RuntimeClass::GetWeakReference metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
dev_langs:
- C++
helpviewer_keywords:
- GetWeakReference method
ms.assetid: 26656ace-7f20-4364-87c9-4a75dd30912e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb0d5e6ca19749a4647ec85311e1fce0e7561b59
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608540"
---
# <a name="runtimeclassgetweakreference-method"></a>RuntimeClass::GetWeakReference Metodu
Geçerli zayıf başvuru nesnesine bir işaretçi alır **RuntimeClass** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   GetWeakReference  
)(_Deref_out_ IWeakReference **weakReference);  
```  
  
### <a name="parameters"></a>Parametreler  
 *weakReference*  
 Bu işlem tamamlandığında zayıf başvuru nesnesine bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Her zaman S_OK.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [RuntimeClass Sınıfı](../windows/runtimeclass-class.md)