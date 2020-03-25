---
title: RuntimeClassType Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 53f0172968c28762bb1305e274bbd47494cdaf4c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213583"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType Numaralandırması

Desteklenen [RuntimeClass](runtimeclass-class.md) örneğinin türünü belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RuntimeClassType;
```

## <a name="members"></a>Üyeler

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`ClassicCom`|Klasik bir COM çalışma zamanı sınıfı.|
|`Delegate`|`ClassicCom`eşdeğerdir.|
|`InhibitFtmBase`|`__WRL_CONFIGURATION_LEGACY__` tanımlanmadığı sırada `FtmBase` desteğini devre dışı bırakır.|
|`InhibitWeakReference`|Zayıf başvuru desteğini devre dışı bırakır.|
|`WinRt`|Windows Çalışma Zamanı sınıfı.|
|`WinRtClassicComMix`|`WinRt` ve `ClassicCom`birleşimi.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)
