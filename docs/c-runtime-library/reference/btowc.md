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
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740011"
---
# <a name="btowc"></a>btowc

Bir tamsayının ilk kaydırma durumunda geçerli bir tek baytlık karakteri temsil edip etmediğini belirleme.

## <a name="syntax"></a>Sözdizimi

```C
wint_t btowc(
   int character
);
```

### <a name="parameters"></a>Parametreler

*inde*<br/>
Sınanacak tamsayı.

## <a name="return-value"></a>Dönüş Değeri

Tamsayı, ilk kaydırma durumunda geçerli bir tek baytlık karakteri temsil ediyorsa karakterin geniş karakter gösterimini döndürür. Tamsayı EOF veya ilk kaydırma durumunda geçerli tek baytlık bir karakter değilse, WEOF döndürür. Bu işlevin çıktısı geçerli **LC_TYPE** yerel ayarından etkilenir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**btowc**|\<stdio. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
