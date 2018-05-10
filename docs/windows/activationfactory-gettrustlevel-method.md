---
title: ActivationFactory::GetTrustLevel yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1e4dfbfbc146663722eba1302b27e96812d684f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="activationfactorygettrustlevel-method"></a>ActivationFactory::GetTrustLevel Metodu
Geçerli ActivationFactory başlatır nesne güven düzeyini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `trustLvl`  
 Bu işlem tamamlandığında, güven düzeyi çalışma zamanı sınıfının ActivationFactory başlatır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi halde, bir onaylama hata yayılan ve `trustLvl` için FullTrust ayarlanır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActivationFactory Sınıfı](../windows/activationfactory-class.md)