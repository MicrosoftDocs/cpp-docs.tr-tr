---
description: 'Daha fazla bilgi edinin: btowc'
title: btowc
ms.date: 4/2/2020
api_name:
- btowc
- _o_btowc
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- btowc
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
ms.openlocfilehash: bbd6121499e03c356e80e49cbcbe75929ca96c2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97171731"
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

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**btowc**|\<stdio.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
