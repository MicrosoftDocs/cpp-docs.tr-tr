---
title: SimpleActivationFactory::GetTrustLevel yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
dev_langs:
- C++
ms.assetid: 99aa9bc9-d954-4a6f-902b-4abe00e43039
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b08ce574a8370eb0029a702f8fa4a4b12c6e93c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="simpleactivationfactorygettrustlevel-method"></a>SimpleActivationFactory::GetTrustLevel Metodu
Tarafından belirtilen sınıfının bir örneği güven düzeyini alır `Base` sınıfı şablon parametresi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `trustLvl`  
 Bu işlem tamamlandığında, geçerli sınıf nesnesi güven düzeyi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Her zaman S_OK.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SimpleActivationFactory Sınıfı](../windows/simpleactivationfactory-class.md)