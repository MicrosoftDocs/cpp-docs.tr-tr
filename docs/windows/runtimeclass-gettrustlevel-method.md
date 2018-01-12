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
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 89a00c052ec1191cd57057f52401954397169b88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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

[RuntimeClass Sınıfı](../windows/runtimeclass-class.md)