---
title: setvbuf sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
dev_langs:
- C++
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a367522c2f22007abcf24cdf74ada467d94b104
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032828"
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