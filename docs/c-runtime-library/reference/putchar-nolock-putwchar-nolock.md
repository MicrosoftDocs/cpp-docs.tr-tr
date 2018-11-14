---
title: _putchar_nolock, _putwchar_nolock
ms.date: 11/04/2016
apiname:
- _putchar_nolock
- _putwchar_nolock
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
apitype: DLLExport
f1_keywords:
- putwchar_nolock
- _puttchar_nolock
- _putchar_nolock
- _putwchar_nolock
- putchar_nolock
helpviewer_keywords:
- _puttchar_nolock function
- putchar_nolock function
- characters, writing
- standard output, writing to
- putwchar_nolock function
- _putchar_nolock function
- _putwchar_nolock function
- puttchar_nolock function
ms.assetid: 9ac68092-bfc3-4352-b486-c3e780220575
ms.openlocfilehash: 2a70c2363b5ae35faab9a0167200366b286408b3
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51517873"
---
# <a name="putcharnolock-putwcharnolock"></a>_putchar_nolock, _putwchar_nolock

Bir karakter Yazar **stdout** iş parçacığını kilitlemeden.

## <a name="syntax"></a>Sözdizimi

```C
int _putchar_nolock(
   int c
);
wint_t _putwchar_nolock(
   wchar_t c
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Yazılacak karakter.

## <a name="return-value"></a>Dönüş Değeri

Bkz: **putchar, putwchar**.

## <a name="remarks"></a>Açıklamalar

**putchar_nolock** ve **_putwchar_nolock** sürümlerle özdeştir **_nolock** soneki olmayan bunlar başka iş parçacıklarının engellemelerinden korunmamaları. Diğer iş parçacıklarını kilitleme ek yükü kalmadıklarından daha hızlı olabilir. Bu işlevler yalnızca tek iş parçacıklı uygulamalar ve burada çağırma kapsamının iş parçacığı yalıtımını zaten işlediği gibi iş parçacığı bakımından güvenli bağlamlarda kullanın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_puttchar_nolock**|**_putchar_nolock**|**_putchar_nolock**|**_putwchar_nolock**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_putchar_nolock**|\<stdio.h >|
|**_putwchar_nolock**|\<stdio.h > veya \<wchar.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsolları ile ilişkili standart akış işleyicileri **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_putchar_nolock.c
/* This program uses putchar to write buffer
* to stdout. If an error occurs, the program
* stops before writing the entire buffer.
*/

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char *p, buffer[] = "This is the line of output\n";
   int  ch;

   ch = 0;

   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )
      ch = _putchar_nolock( *p );
}
```

### <a name="output"></a>Çıkış

```Output
This is the line of output
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
