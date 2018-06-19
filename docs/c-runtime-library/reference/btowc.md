---
title: btowc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- btowc
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- btowc
dev_langs:
- C++
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d0e56649218e6249550638af4e198cbd1284bc2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393322"
---
# <a name="btowc"></a>btowc

Tamsayı ilk kaydırma durumda geçerli bir tek baytlı karakter temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
wint_t btowc(
   int character
);
```

### <a name="parameters"></a>Parametreler

*Karakter*<br/>
Test etmek için bir tamsayı.

## <a name="return-value"></a>Dönüş Değeri

Geçerli bir tek baytlı karakter ilk kaydırma durumda tamsayı temsil ediyorsa karakter joker karakter gösterimini döndürür. Tamsayı EOF ya da geçerli bir tek baytlı karakter ilk kaydırma durumda değil ise WEOF döndürür. Bu işlev çıktısını geçerli tarafından etkilenen **LC_TYPE** yerel ayar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**btowc**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
