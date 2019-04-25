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
ms.openlocfilehash: 28c9debf7e51d06cb9a625bb0a52d578ce3142c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62268930"
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

## <a name="see-also"></a>Ayrıca bkz.

[setbuf](../c-runtime-library/reference/setbuf.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)
