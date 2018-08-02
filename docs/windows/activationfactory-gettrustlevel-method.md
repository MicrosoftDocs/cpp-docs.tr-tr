---
title: ActivationFactory::GetTrustLevel metodu | Microsoft Docs
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
ms.openlocfilehash: af3ec58afd69f3fde6e2eb67969f1dad8848c5de
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466728"
---
# <a name="activationfactorygettrustlevel-method"></a>ActivationFactory::GetTrustLevel Metodu
Nesne güven düzeyini alır Geçerli **ActivationFactory** başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *trustLvl*  
 Bu işlem tamamlandığında, çalışma zamanı güven düzeyini sınıfı, **ActivationFactory** başlatır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, bir onaylama işlemi hatası yayılır ve *trustLvl* FullTrust için ayarlanır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActivationFactory Sınıfı](../windows/activationfactory-class.md)