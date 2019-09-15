---
title: btowc
ms.date: 11/04/2016
api_name:
- btowc
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- btowc
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
ms.openlocfilehash: 1f03fce8686f919af85ee3751cb9a0a3fca1ede7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943464"
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
