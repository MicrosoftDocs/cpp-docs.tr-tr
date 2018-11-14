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
ms.openlocfilehash: 661cf64c71e06c222503388df198d47429566602
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523812"
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