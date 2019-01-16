---
title: AsyncResultType Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
ms.openlocfilehash: 309ed876c71f453336ecc2ed10eedc07f2a80be8
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54334950"
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

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)