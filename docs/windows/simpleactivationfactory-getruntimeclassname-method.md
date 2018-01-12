---
title: "SimpleActivationFactory::GetRuntimeClassName yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
dev_langs: C++
ms.assetid: 3aa07487-9a42-46f8-8893-37ba6315e50b
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 73431c7a0f719579caf3df146b69dd8d7248d0a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="simpleactivationfactorygetruntimeclassname-method"></a>SimpleActivationFactory::GetRuntimeClassName Metodu

Tarafından belirtilen sınıfının bir örneğini çalışma zamanı sınıf adını alır `Base` sınıfı şablon parametresi.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>Parametreler

*runtimeName*  
Bu işlem tamamlandığında, çalışma zamanı sınıf adı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, HRESULT hata gösterir.

## <a name="remarks"></a>Açıklamalar

Varsa &#95; &#95; WRL_STRICT &#95; &#95; olduğundan sınıfı tarafından belirtilmişse tanımlanan assert hata yayılan `Base` değil sınıfı şablon parametresi türetilen [RuntimeClass](../windows/runtimeclass-class.md), ya da WinRt veya WinRtClassicComMix ile yapılandırılmamış [ RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırma değeri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[SimpleActivationFactory Sınıfı](../windows/simpleactivationfactory-class.md)