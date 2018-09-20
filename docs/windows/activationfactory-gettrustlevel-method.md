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
ms.openlocfilehash: eba02bea09784e3431b3697eb9ac9a47de978348
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424566"
---
# <a name="activationfactorygettrustlevel-method"></a>ActivationFactory::GetTrustLevel Metodu

Nesne güven düzeyini alır Geçerli **ActivationFactory** başlatır.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>Parametreler

*trustLvl*<br/>
Bu işlem tamamlandığında, çalışma zamanı güven düzeyini sınıfı, **ActivationFactory** başlatır.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, bir onaylama işlemi hatası yayılır ve *trustLvl* ayarlanır `FullTrust`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[ActivationFactory Sınıfı](../windows/activationfactory-class.md)