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
ms.openlocfilehash: 0d4292ae29602b5890a167a3e2c29e460d65373f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="setvbuf-constants"></a>setvbuf Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <stdio.h>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sabitleri için arabellek türünü temsil eden `setvbuf`.  
  
 Olası değerler aşağıdaki bildirim sabitler tarafından verilir:  
  
|Sabit|Açıklama|  
|--------------|-------------|  
|`_IOFBF`|Tam arabelleğe alma: Arabellek belirtilen çağrıda `setvbuf` kullanılır ve kendi boyuttur olarak belirtilen `setvbuf` çağırın. Arabellek işaretçi ise **NULL**, otomatik olarak ayrılmış arabellek belirtilen boyutunu kullanılır.|  
|`_IOLBF`|Aynı `_IOFBF`.|  
|`_IONBF`|Hiçbir arabellek çağrısı değişkenlerinde bağımsız olarak kullanılır `setvbuf`.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [setbuf](../c-runtime-library/reference/setbuf.md)   
 [Global Sabitler](../c-runtime-library/global-constants.md)