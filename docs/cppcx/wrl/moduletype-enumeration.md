---
title: ModuleType Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
ms.openlocfilehash: 8425a15d594f7b8b30027d3576ee86015b656130
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213726"
---
# <a name="moduletype-enumeration"></a>ModuleType Numaralandırması

Modülün işlem içi bir sunucuyu mı yoksa işlem dışı bir sunucuyu mı desteklemesi gerektiğini belirtir.

## <a name="syntax"></a>Sözdizimi

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
|`InProcDisableCaching`|`InProc` ve `DisableCaching`birleşimi.|
|`OutOfProcDisableCaching`|`OutOfProc` ve `DisableCaching`birleşimi.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)
