---
description: 'Daha fazla bilgi edinin: RuntimeClassType numaralandırması'
title: RuntimeClassType Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 10055d79148124e886c4da50e40ffdb7d3d0fec0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135284"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType Numaralandırması

Desteklenen [RuntimeClass](runtimeclass-class.md) örneğinin türünü belirtir.

## <a name="syntax"></a>Syntax

```cpp
enum RuntimeClassType;
```

## <a name="members"></a>Üyeler

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`ClassicCom`|Klasik bir COM çalışma zamanı sınıfı.|
|`Delegate`|İle eşdeğerdir `ClassicCom` .|
|`InhibitFtmBase`|`FtmBase`Tanımlı olmayan desteği devre dışı bırakır `__WRL_CONFIGURATION_LEGACY__` .|
|`InhibitWeakReference`|Zayıf başvuru desteğini devre dışı bırakır.|
|`WinRt`|Windows Çalışma Zamanı sınıfı.|
|`WinRtClassicComMix`|`WinRt`Ve birleşimi `ClassicCom` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)
