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
ms.openlocfilehash: 25c25741f54c1383a5bad9038b5b5d761dacdd89
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458060"
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
|`_IOFBF`|Tam arabelleğe alma: Belirtilen arabellek çağrıda `setvbuf` kullanılır ve boyutunu olarak belirtilen `setvbuf` çağırın. Arabellek işaretçi işaret türündeyse **NULL**, otomatik olarak tahsis edilen arabellek belirtilen boyutu kullanılır.|
|`_IOLBF`|Aynı `_IOFBF`.|
|`_IONBF`|Arabellek çağrısında bağımsız değişken bağımsız olarak kullanılır `setvbuf`.|

## <a name="see-also"></a>Ayrıca Bkz.

[setbuf](../c-runtime-library/reference/setbuf.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)