---
title: _swab
ms.date: 4/2/2020
api_name:
- _swab
- stdlib/_swab
- _o__swab
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
- api-ms-win-crt-utility-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _swab
- stdlib/_swab
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
ms.openlocfilehash: f7fe23cd9c1b2eab52ebe50904d0bb18fe16cea6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362961"
---
# <a name="_swab"></a>_swab

Bayt takas eder.

## <a name="syntax"></a>Sözdizimi

```C
void _swab(
   char *src,
   char *dest,
   int n
);
```

## <a name="parameters"></a>Parametreler

*src*<br/>
Kopyalanacak ve değiştirilecek veriler.

*Dest*<br/>
Değiştirilen veriler için depolama konumu.

*n*<br/>
Kopyalanacak ve değiştirilecek bayt sayısı.

## <a name="return-value"></a>Döndürülen değer

**Bez** işlevi bir değer döndürmez. *Src* veya *dest* işaretçisi null veya *n* sıfırdan az ise **işlev,** **EINVAL** olarak ayarlar ve geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

*n* eşitse, **_swab** işlevi *src'den* *n* bayt kopyalar, bitişik baytların her çiftini değiştirir ve sonucu *destte*depolar. *N* tek ise, **_swab** kopyalar ve *src*ilk *n*-1 bayt takas ve son bayt kopyalanmaz. **_swab** işlevi genellikle farklı bir bayt siparişi kullanan bir makineye aktarım için ikili veri hazırlamak için kullanılır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_swab**|C: \<stdlib.h> \<C++: cstdlib> veya \<stdlib.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_swab.c

#include <stdlib.h>
#include <stdio.h>

char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";
char to[] =   "...........................";

int main()
{
    printf("Before: %s  %d bytes\n        %s\n\n", from, sizeof(from), to);
    _swab(from, to, sizeof(from));
    printf("After:  %s\n        %s\n\n", from, to);
}
```

```Output
Before: BADCFEHGJILKNMPORQTSVUXWZY  27 bytes
        ...........................

After:  BADCFEHGJILKNMPORQTSVUXWZY
        ABCDEFGHIJKLMNOPQRSTUVWXYZ.
```

## <a name="see-also"></a>Ayrıca bkz.

[Arabellek Manipülasyonu](../../c-runtime-library/buffer-manipulation.md)<br/>
