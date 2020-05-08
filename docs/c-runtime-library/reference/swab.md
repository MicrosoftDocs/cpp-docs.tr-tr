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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 7353081fab92fcc3324a214688be28a4f651b05f
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912421"
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

*src*<br/>
Kopyalanacak ve takas edilecek veriler.

*HD*<br/>
Takas edilen veriler için depolama konumu.

*No*<br/>
Kopyalanacak ve takas edilecek bayt sayısı.

## <a name="return-value"></a>Döndürülen değer

**Swab** işlevi bir değer döndürmüyor. *Src* veya *dest* işaretçisi null ya da *n* sıfırdan küçükse ve [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi, geçersiz parametre işleyicisi çağrıldığında, işlev **errno** 'ya **EINVAL** olarak ayarlar.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

*N* çift ise, **_swab** işlevi *src*'den *n* bayt kopyalar, her bir çift ardışık bayt çiftini değiştirir ve sonucu *hedef*olarak depolar. *N* tek ise, **_swab** *src*'nin ilk *n*-1 baytını kopyalar ve değiştirir ve son bayt kopyalanmaz. **_Swab** işlevi, genellikle ikili verileri farklı bir bayt sırası kullanan bir makineye aktarmak üzere hazırlamak için kullanılır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_swab**|C: \<Stdlib. h> C++: \<cstdlib> veya \<Stdlib. h>|

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

[Arabellek Işleme](../../c-runtime-library/buffer-manipulation.md)<br/>
