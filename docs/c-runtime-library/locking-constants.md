---
title: _locking Sabitleri
ms.date: 11/04/2016
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
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
ms.openlocfilehash: 721e2433a6d7a76ad73b0f52f033c3e04cab8f6d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526362"
---
# <a name="locking-constants"></a>_locking Sabitleri

## <a name="syntax"></a>Sözdizimi

```
#include <sys/locking.h>
```

## <a name="remarks"></a>Açıklamalar

*Modu* çağrısında bağımsız değişken `_locking` işlevi kilitleme gerçekleştirilecek eylemi belirtir.

*Modu* bağımsız değişkeni aşağıdaki bildirim sabitleri biri olması gerekir.

|||
|-|-|
| `_LK_LOCK`  | Belirtilen bayt kilitler. Bayt kilitlenemez, işlev 1 saniye sonra yeniden çalışır. 10 denemeden sonra bayt kilitlenemez, işlev hata döndürür.  |
| `_LK_RLCK`  | Aynı `_LK_LOCK`.  |
|`_LK_NBLCK`  | Belirtilen bayt kilitler. Bayt kilitlenemez, işlev hata döndürür.  |
| `_LK_NBRLCK`  | Aynı `_LK_NBLCK`.  |
| `_LK_UNLCK`  | Belirtilen bayt kilidini açar. (Bayt önceden kilitlenmiş gerekir.)  |

## <a name="see-also"></a>Ayrıca Bkz.

[_locking](../c-runtime-library/reference/locking.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)