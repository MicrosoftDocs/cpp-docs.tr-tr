---
description: 'Daha fazla bilgi edinin: AsyncResultType numaralandırması'
title: AsyncResultType Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
ms.openlocfilehash: 431c0cabf98b3636bbae02b2f05a14d11d122740
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175826"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType Numaralandırması

Yöntem tarafından döndürülen sonuç türünü belirtir `GetResults()` .

## <a name="syntax"></a>Syntax

```cpp
enum AsyncResultType;
```

## <a name="members"></a>Üyeler

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`MultipleResults`|Durum ve Before arasında aşamalı olarak sunulan birden çok sonuç kümesi `Start` `Close()` .|
|`SingleResult`|Olay oluştuktan sonra sunulan tek bir sonuç `Complete` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** Async. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)
