---
title: _locking sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
dev_langs:
- C++
helpviewer_keywords:
- LK_UNLCK constant
- LK_NBRLCK constant
- _LK_NBRLCK constant
- _LK_NBLCK constant
- _LK_LOCK constant
- LK_NBLCK constant
- _LK_UNLCK constant
- LK_RLCK constant
- _LK_RLCK constant
- LK_LOCK constant
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 588c286cbad5e0097394a38eed34c09fc04af3ea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389975"
---
# <a name="locking-constants"></a>_locking Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <sys/locking.h>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 *Modu* çağrısında bağımsız değişkeni `_locking` işlevi gerçekleştirilecek kilitleme eylemi belirtir.  
  
 *Modu* bağımsız değişkeni aşağıdaki bildirim sabitlerden biri olması gerekir.  
  
 `_LK_LOCK`  
 Belirtilen bayt kilitler. Bayt kilitlenemez varsa, işlev 1 saniye sonra yeniden çalışır. 10 denemeden sonra bayt kilitlenemez varsa, işlev hata döndürür.  
  
 `_LK_RLCK`  
 Aynı `_LK_LOCK`.  
  
 `_LK_NBLCK`  
 Belirtilen bayt kilitler. Bayt kilitlenemez, işlev hata döndürür.  
  
 `_LK_NBRLCK`  
 Aynı `_LK_NBLCK`.  
  
 `_LK_UNLCK`  
 Belirtilen bayt kilidini açar. (Bayt önceden kilitlenen gerekir.)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_locking](../c-runtime-library/reference/locking.md)   
 [Global Sabitler](../c-runtime-library/global-constants.md)