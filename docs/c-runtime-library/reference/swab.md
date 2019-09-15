---
title: _swab
ms.date: 11/04/2016
api_name:
- _swab
- stdlib/_swab
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
ms.openlocfilehash: b0faba55c42023f4d66adae68de6be2c1ab009a0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946285"
---
# <a name="_swab"></a>_swab

Baytları değiştirir.

## <a name="syntax"></a>Sözdizimi

```C
void _swab(
   char *src,
   char *dest,
   int n
);
```

## <a name="parameters"></a>Parametreler

*YN*<br/>
Kopyalanacak ve takas edilecek veriler.

*HD*<br/>
Takas edilen veriler için depolama konumu.

*n*<br/>
Kopyalanacak ve takas edilecek bayt sayısı.

## <a name="return-value"></a>Dönüş değeri

**Swab** işlevi bir değer döndürmüyor. *Src* veya *dest* işaretçisi null ya da *n* sıfırdan küçükse ve [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi, geçersiz parametre işleyicisi çağrıldığında, işlev **errno** 'ya **EINVAL** olarak ayarlar.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

*N* bile çiftse, **_swab** işlevi *src*'den *n* bayt kopyalar, her bir çift komşu bayt çiftini değiştirir ve sonucu *hedef*olarak depolar. *N* tek ise, **_swab** , *src*'nin ilk *n*-1 baytını kopyalar ve değiştirir ve son bayt kopyalanmaz. **_Swab** işlevi, genellikle ikili verileri farklı bir bayt sırası kullanan bir makineye aktarmak üzere hazırlamak için kullanılır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_swab**|C: \<Stdlib. h > C++: \<cstdlib > veya \<Stdlib. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Ara Bellek Düzenlemesi](../../c-runtime-library/buffer-manipulation.md)<br/>
