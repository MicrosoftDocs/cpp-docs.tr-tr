---
title: AsyncResultType Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
ms.openlocfilehash: df91b80fe21ecddabc7062b040387b8c2b2c1bb7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551378"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType Numaralandırması

Tarafından döndürülen sonuç türü belirtir `GetResults()` yöntemi.

## <a name="syntax"></a>Sözdizimi

```cpp
enum AsyncResultType;
```

## <a name="members"></a>Üyeler

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`MultipleResults`|Bir aşamalı olarak arasında sunulan birden çok sonuç kümesi `Start` durumu ve önce `Close()` çağrılır.|
|`SingleResult`|Sonra sunulan tek bir sonuç `Complete` olayı oluşur.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)