---
title: _acmdln, _tcmdln, _wcmdln
ms.date: 11/04/2016
apiname:
- _wcmdln
- _acmdln
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _acmdln
- acmdln
- _wcmdln
- wcmdln
- _tcmdln
- tcmdln
helpviewer_keywords:
- _wcmdln global variable
- wcmdln global variable
- _acmdln global variable
- _tcmdln global variable
- tcmdln global variable
- acmdln global variable
ms.assetid: 4fc0a6a0-3f93-420a-a19f-5276061ba539
ms.openlocfilehash: 519cfb305d0092907ff8f10d2b66429a260a5fe2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668058"
---
# <a name="acmdln-tcmdln-wcmdln"></a>_acmdln, _tcmdln, _wcmdln

İç CRT genel değişkeni. Komut satırı.

## <a name="syntax"></a>Sözdizimi

```
char * _acmdln;
wchar_t * _wcmdln;

#ifdef WPRFLAG
   #define _tcmdln _wcmdln
#else
   #define _tcmdln _acmdln
```

## <a name="remarks"></a>Açıklamalar

Bu CRT iç değişkenler, tam komut satırı depolayın. Dışarı aktarılan sembolleri için CRT gösterilir, ancak kodunuzda kullanmak için tasarlanmamıştır. `_acmdln` bir karakter dizisi olarak verileri depolar. `_wcmdln` verileri bir geniş karakter dizesi depolar. `_tcmdln` olarak tanımlanabilir `_acmdln` veya `_wcmdln`uygun olduğu bağlı olarak.

## <a name="see-also"></a>Ayrıca Bkz.

[Global Değişkenler](../c-runtime-library/global-variables.md)