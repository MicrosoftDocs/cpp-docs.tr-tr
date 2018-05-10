---
title: RuntimeClass::GetTrustLevel yöntemi | Microsoft Docs
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
ms.openlocfilehash: bc588950cc8752a7c2b8e1ddf00b2193aaf0f395
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="runtimeclassgettrustlevel-method"></a>RuntimeClass::GetTrustLevel Metodu

Geçerli RuntimeClass nesne güven düzeyini alır.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>Parametreler

*trustLvl*  
Bu işlem tamamlandığında geçerli RuntimeClass nesnesinin güven düzeyi.

## <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK.

## <a name="remarks"></a>Açıklamalar

Assert hata durumunda yayılan &#95; &#95;WRL_STRICT&#95; &#95; veya &#95; &#95;WRL_FORCE_INSPECTABLE_CLASS_MACRO&#95; &#95; tanımlı değil.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[RuntimeClass Sınıfı](../windows/runtimeclass-class.md)