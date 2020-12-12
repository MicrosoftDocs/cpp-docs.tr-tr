---
description: 'Daha fazla bilgi edinin: setvarabelleğe sabitleri'
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
ms.openlocfilehash: 375c692f4437bd60c84e37c857e078d9386ffb1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277017"
---
# <a name="setvbuf-constants"></a>setvbuf Sabitleri

## <a name="syntax"></a>Syntax

```
#include <stdio.h>
```

## <a name="remarks"></a>Açıklamalar

Bu sabitler, için arabellek türünü temsil eder `setvbuf` .

Olası değerler aşağıdaki bildirim sabitleri tarafından verilir:

|Sabit|Anlamı|
|--------------|-------------|
|`_IOFBF`|Tam arabelleğe alma: öğesine yapılan çağrıda belirtilen arabellek `setvbuf` kullanılır ve bu boyut `setvbuf` çağrısında belirtilmiştir. Arabellek işaretçisi **null** ise, belirtilen boyuttaki otomatik olarak ayrılan arabellek kullanılır.|
|`_IOLBF`|Aynı `_IOFBF` .|
|`_IONBF`|Çağrısındaki bağımsız değişkenlerle bağımsız olarak hiçbir arabellek kullanılmaz `setvbuf` .|

## <a name="see-also"></a>Ayrıca bkz.

[setbuf](../c-runtime-library/reference/setbuf.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
