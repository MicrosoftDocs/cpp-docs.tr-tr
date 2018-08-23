---
title: SimpleActivationFactory::GetRuntimeClassName metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
dev_langs:
- C++
ms.assetid: 3aa07487-9a42-46f8-8893-37ba6315e50b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e66c6791a55debeb411fd6058d4bbe44cb6637e7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42575878"
---
# <a name="simpleactivationfactorygetruntimeclassname-method"></a>SimpleActivationFactory::GetRuntimeClassName Metodu

Çalışma zamanı sınıf adı tarafından belirtilen sınıfın örneğini alır `Base` sınıfı şablon parametresi.

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

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="remarks"></a>Açıklamalar

Varsa `__WRL_STRICT__` olan sınıfın belirtilen tanımlanan, bir onay hatası yayılır `Base` olmayan şablon parametresi sınıf türetilmiş [RuntimeClass](../windows/runtimeclass-class.md), ya da WinRt veya WinRtClassicComMix ileyapılandırılmamış[RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırma değeri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[SimpleActivationFactory Sınıfı](../windows/simpleactivationfactory-class.md)