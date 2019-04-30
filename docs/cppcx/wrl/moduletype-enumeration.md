---
title: ModuleType Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
ms.openlocfilehash: 3c7486cbc761975dd133f229f23dcf0b70e7e3ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403236"
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

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)