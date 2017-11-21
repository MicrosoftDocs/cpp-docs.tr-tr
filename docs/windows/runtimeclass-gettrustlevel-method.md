---
title: "RuntimeClass::GetTrustLevel yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
dev_langs: C++
helpviewer_keywords: GetTrustLevel method
ms.assetid: bd90407e-6dd7-41c3-9ea0-c402c276014a
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bf5125f7f0fdfe6309d668404dd1077e629a4fac
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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

Assert verilmiş IF &#95; &#95;hatadır; WRL_STRICT &#95; &#95; ya &#95; &#95; WRL_FORCE_INSPECTABLE_CLASS_MACRO &#95; &#95; tanımlı değil.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[RuntimeClass sınıfı](../windows/runtimeclass-class.md)