---
title: btowc
ms.date: 11/04/2016
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
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
ms.openlocfilehash: 399f56fe133a9f67ed457b435ae6c0496e1ecaa5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514688"
---
# <a name="btowc"></a>btowc

Geçerli bir tek baytlı karakter ilk shift durumunda bir tamsayı temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
wint_t btowc(
   int character
);
```

### <a name="parameters"></a>Parametreler

*Karakter*<br/>
Test edilecek tamsayı.

## <a name="return-value"></a>Dönüş Değeri

Geçerli bir tek baytlı karakter ilk shift durumunda tamsayıyı temsil ediyorsa karakterinin geniş karakter gösterimi döndürür. Tamsayı EOF veya geçerli bir tek baytlı karakter ilk shift durumunda değil WEOF döndürür. Bu işlevin çıktısı geçerli tarafından etkilenir **LC_TYPE** yerel ayar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**btowc**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
