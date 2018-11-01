---
title: RuntimeClassType Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 62a82d5fab9fd22e23a5244d4fda3b7f5202304c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626817"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType Numaralandırması

Türünü belirten [RuntimeClass](../windows/runtimeclass-class.md) desteklenen örneği.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RuntimeClassType;
```

## <a name="members"></a>Üyeler

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`ClassicCom`|Klasik COM çalışma zamanı sınıf.|
|`Delegate`|Eşdeğer `ClassicCom`.|
|`InhibitFtmBase`|Devre dışı bırakır `FtmBase` sırasında Destek `__WRL_CONFIGURATION_LEGACY__` tanımlı değil.|
|`InhibitWeakReference`|Zayıf başvuru desteği devre dışı bırakır.|
|`WinRt`|Bir Windows çalışma zamanı sınıf.|
|`WinRtClassicComMix`|Bir birleşimi `WinRt` ve `ClassicCom`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)