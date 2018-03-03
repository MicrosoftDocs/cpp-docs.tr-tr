---
title: setvbuf sabitleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6bdb0fd3ad3811e756458090a963f78bd716a581
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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