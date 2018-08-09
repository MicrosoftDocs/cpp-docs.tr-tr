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
ms.openlocfilehash: adcec3f4a531a6c48e0995468994900124746e4b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015137"
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

Assert hata durumunda yayıldığını `__WRL_STRICT__` veya `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` tanımlanmadı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.
 [RuntimeClass Sınıfı](../windows/runtimeclass-class.md)