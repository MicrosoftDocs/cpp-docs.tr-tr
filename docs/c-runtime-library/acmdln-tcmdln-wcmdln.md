---
title: _acmdln, _tcmdln, _wcmdln
ms.date: 11/04/2016
api_name:
- _wcmdln
- _acmdln
api_location:
- msvcrt.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 07061244e06256341a6da7d04e5487e81c4b9378
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940608"
---
# <a name="_acmdln-_tcmdln-_wcmdln"></a>_acmdln, _tcmdln, _wcmdln

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

Bu CRT iç değişkenleri komut satırının tamamını depolar. Bu karakterler CRT için aktarılmış semboller içinde sunulur, ancak kodunuzda kullanılmak üzere tasarlanmamıştır. `_acmdln`verileri bir karakter dizesi olarak depolar. `_wcmdln`verileri geniş bir karakter dizesi olarak depolar. `_tcmdln`, uygun olduğuna bağlı olarak `_acmdln` veya `_wcmdln`olarak tanımlanabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Global Değişkenler](../c-runtime-library/global-variables.md)
