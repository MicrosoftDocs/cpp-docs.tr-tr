---
title: _fgetchar, _fgetwchar
ms.date: 11/04/2016
apiname:
- _fgetchar
- _fgetwchar
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fgetwchar
- _fgettchar
- _fgetchar
- _fgetwchar
- fgettchar
helpviewer_keywords:
- fgetwchar function
- _fgetchar function
- fgettchar function
- _fgetwchar function
- _fgettchar function
- standard input, reading from
- fgetchar function
ms.assetid: 8bce874c-701a-41a3-b1b2-feff266fb5b9
ms.openlocfilehash: c74618fa0be5392062d13618ff73e2ef45bf7c2a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333962"
---
# <a name="fgetchar-fgetwchar"></a>_fgetchar, _fgetwchar

Bir karakter okur **stdin**.

## <a name="syntax"></a>Sözdizimi

```C
int _fgetchar( void );
wint_t _fgetwchar( void );
```

## <a name="return-value"></a>Dönüş Değeri

**\_fgetchar** olarak okuma karakteri döndürür bir **int** veya döndürür `EOF` bir hata veya dosya sonunu belirtmek için. **\_fgetwchar** döndürür, olarak bir [wint_t](../../c-runtime-library/standard-types.md), döndürür veya okuma karakterine karşılık gelen geniş karakter `WEOF` bir hata veya dosya sonunu belirtmek için. Her iki işlev için kullanmak **feof** veya **ferror** hata ve bir dosya sonu koşulunu ayırt etmek için.

## <a name="remarks"></a>Açıklamalar

Bu işlevleri tek bir karakter okur **stdin**. İşlevi ardından ilgili dosya işaretleyicisini (tanımlıysa) sonraki karaktere işaret etmek üzere artırır. Akış dosya sonunda ise, akış için dosya sonu göstergesi ayarlanır.

**_fgetchar** eşdeğerdir `fgetc( stdin )`. Ayrıca değerine eşdeğer olan **getchar**, ancak bir işlev ve makro olarak değil, yalnızca işlev olarak uygulanır. **_fgetwchar** öğesinin geniş karakterli sürümüdür **_fgetchar**.

Bu işlevler ANSI standardı ile uyumlu değildir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_fgettchar**|**_fgetchar**|**_fgetchar**|**_fgetwchar**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fgetchar**|\<stdio.h >|
|**_fgetwchar**|\<stdio.h > veya \<wchar.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsolları ile ilişkili standart akış işleyicileri —**stdin**, **stdout**, ve **stderr**— C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmesi gerekiyor . Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fgetchar.c
// This program uses _fgetchar to read the first
// 80 input characters (or until the end of input)
// and place them into a string named buffer.
//

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char buffer[81];
   int  i, ch;

   // Read in first 80 characters and place them in "buffer":
   ch = _fgetchar();
   for( i=0; (i < 80 ) && ( feof( stdin ) == 0 ); i++ )
   {
      buffer[i] = (char)ch;
      ch = _fgetchar();
   }

   // Add null to end string
   buffer[i] = '\0';
   printf( "%s\n", buffer );
}
```

```Output

      Line one.
Line two.Line one.
Line two.
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
