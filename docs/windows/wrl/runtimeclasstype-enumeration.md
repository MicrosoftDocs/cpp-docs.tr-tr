---
title: RuntimeClassType Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 3b869be00cdc405569b82bdf3730f8d4ca4f3aab
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335226"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType Numaralandırması

Türünü belirten [RuntimeClass](runtimeclass-class.md) desteklenen örneği.

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

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)