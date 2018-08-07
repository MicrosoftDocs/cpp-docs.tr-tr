---
title: RuntimeClass::GetTrustLevel metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: bd90407e-6dd7-41c3-9ea0-c402c276014a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 98bd73d2c067e6d5bbb4425782de594bbaa47bc1
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606630"
---
# <a name="runtimeclassgettrustlevel-method"></a>RuntimeClass::GetTrustLevel Metodu

Geçerli güven düzeyine alır **RuntimeClass** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>Parametreler

*trustLvl*  
Bu işlem tamamlandığında, geçerli güven düzeyine **RuntimeClass** nesne.

## <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK.

## <a name="remarks"></a>Açıklamalar

Assert hata durumunda yayıldığını &#95; &#95;WRL_STRICT&#95; &#95; veya &#95; &#95;WRL_FORCE_INSPECTABLE_CLASS_MACRO&#95; &#95; tanımlanmadı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.
 [RuntimeClass Sınıfı](../windows/runtimeclass-class.md)