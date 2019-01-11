---
title: setvbuf Sabitleri
ms.date: 11/04/2016
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
ms.openlocfilehash: 8936789f4e3c9349e9d79616c8506c044dc79f70
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220406"
---
# <a name="setvbuf-constants"></a>setvbuf Sabitleri

## <a name="syntax"></a>Sözdizimi

```
#include <stdio.h>
```

## <a name="remarks"></a>Açıklamalar

Bu sabiti temsil etmek için arabellek türü `setvbuf`.

Olası değerler aşağıdaki bildirim sabitleriyle verilmiştir:

|Sabit|Açıklama|
|--------------|-------------|
|`_IOFBF`|Tam arabelleğe alma: Yapılan çağrıda belirtilen arabellek `setvbuf` kullanılır ve boyutunu olarak belirtilen `setvbuf` çağırın. Arabellek işaretçi işaret türündeyse **NULL**, otomatik olarak tahsis edilen arabellek belirtilen boyutu kullanılır.|
|`_IOLBF`|Aynı `_IOFBF`.|
|`_IONBF`|Arabellek çağrısında bağımsız değişken bağımsız olarak kullanılır `setvbuf`.|

## <a name="see-also"></a>Ayrıca Bkz.

[setbuf](../c-runtime-library/reference/setbuf.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)
