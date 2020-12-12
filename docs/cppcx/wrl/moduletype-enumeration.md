---
description: 'Daha fazla bilgi edinin: ModuleType numaralandırması'
title: ModuleType Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
ms.openlocfilehash: 148f9594fd16a6c8a2af70ac0ff2ac03cd1f62e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209379"
---
# <a name="moduletype-enumeration"></a>ModuleType Numaralandırması

Modülün işlem içi bir sunucuyu mı yoksa işlem dışı bir sunucuyu mı desteklemesi gerektiğini belirtir.

## <a name="syntax"></a>Syntax

```cpp
enum ModuleType;
```

## <a name="members"></a>Üyeler

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`InProc`|İşlem içi sunucu.|
|`OutOfProc`|İşlem dışı bir sunucu.|
|`DisableCaching`|Modül üzerinde önbelleğe alma mekanizmasını devre dışı bırakın.|
|`InProcDisableCaching`|Ve birleşimi `InProc` `DisableCaching` .|
|`OutOfProcDisableCaching`|Ve birleşimi `OutOfProc` `DisableCaching` .|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)
