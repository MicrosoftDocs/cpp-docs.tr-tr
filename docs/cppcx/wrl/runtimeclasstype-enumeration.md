---
title: RuntimeClassType Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 80e8a120f7e3666721ff839a2a696388a64d734e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403144"
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

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)