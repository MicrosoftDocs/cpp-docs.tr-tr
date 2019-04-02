---
title: ModuleType Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
ms.openlocfilehash: 937649eada481f7c45359fa0816266f62dc03875
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787721"
---
# <a name="moduletype-enumeration"></a>ModuleType Numaralandırması

Bir modülü bir işlem sunucusu veya bir işlem dışı sunucu desteklemesi gerekip gerekmediğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
enum ModuleType;
```

## <a name="members"></a>Üyeler

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`InProc`|Bir işlem sunucusu.|
|`OutOfProc`|Bir işlem dışı sunucu.|
|`DisableCaching`|Önbelleğe alma mekanizması modül devre dışı bırakın.|
|`InProcDisableCaching`|Birleşimi `InProc` ve `DisableCaching`.|
|`OutOfProcDisableCaching`|Birleşimi `OutOfProc` ve `DisableCaching`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)