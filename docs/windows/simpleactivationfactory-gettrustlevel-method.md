---
title: "SimpleActivationFactory::GetTrustLevel yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
dev_langs:
- C++
ms.assetid: 99aa9bc9-d954-4a6f-902b-4abe00e43039
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 608f67267b8a82341ff3beb3e27f8e0eb9891c8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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