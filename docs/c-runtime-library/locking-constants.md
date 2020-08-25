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
ms.openlocfilehash: 8cfc1f933179e043f464a69f3ac5cf4ca25763e0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830832"
---
# <a name="_locking-constants"></a>_locking Sabitleri

## <a name="syntax"></a>Syntax

```
#include <sys/locking.h>
```

## <a name="remarks"></a>Açıklamalar

İşlev çağrısındaki *mod* bağımsız değişkeni `_locking` gerçekleştirilecek kilitleme eylemini belirtir.

*Mod* bağımsız değişkeni aşağıdaki bildirim sabitlerinden biri olmalıdır.

|Değer|Açıklama|
|-|-|
| `_LK_LOCK`  | Belirtilen baytları kilitler. Baytlar kilitlenmediyse, işlev 1 saniye sonra yeniden dener. 10 denemeden sonra baytlar kilitlenmediyse, işlev bir hata döndürür.  |
| `_LK_RLCK`  | Aynı `_LK_LOCK` .  |
|`_LK_NBLCK`  | Belirtilen baytları kilitler. Baytlar kilitlenmediyse, işlev bir hata döndürür.  |
| `_LK_NBRLCK`  | Aynı `_LK_NBLCK` .  |
| `_LK_UNLCK`  | Belirtilen baytların kilidini açar. (Baytların daha önce kilitlenmiş olması gerekir.)  |

## <a name="see-also"></a>Ayrıca bkz.

[_locking](../c-runtime-library/reference/locking.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
