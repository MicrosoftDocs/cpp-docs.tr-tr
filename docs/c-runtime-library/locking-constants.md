---
title: _locking sabitleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
dev_langs: C++
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
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 799b00209463c90c61b4b497a88af39ba554cd01
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Genel sabitler](../c-runtime-library/global-constants.md)