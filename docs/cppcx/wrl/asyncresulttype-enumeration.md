---
title: AsyncResultType Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
ms.openlocfilehash: b8a2a9ec803fba1be0012fcb58bf3b42e78f9071
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214168"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType Numaralandırması

`GetResults()` yöntemi tarafından döndürülen sonuç türünü belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
enum AsyncResultType;
```

## <a name="members"></a>Üyeler

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`MultipleResults`|`Start` durumu ve `Close()` çağrılmadan önce aşamalı olarak sunulan birden çok sonuç kümesi.|
|`SingleResult`|`Complete` olayı oluştuktan sonra sunulan tek bir sonuç.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** Async. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)
