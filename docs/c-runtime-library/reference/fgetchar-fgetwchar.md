---
title: _fgetchar, _fgetwchar
ms.date: 4/2/2020
api_name:
- _fgetchar
- _fgetwchar
- _o__fgetchar
- _o__fgetwchar
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: b9d805483395d3050a1eb0bc78afef8cd99ca984
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346926"
---
# <a name="_fgetchar-_fgetwchar"></a>_fgetchar, _fgetwchar

**Stdin**bir karakter okur.

## <a name="syntax"></a>Sözdizimi

```C
int _fgetchar( void );
wint_t _fgetwchar( void );
```

## <a name="return-value"></a>Dönüş Değeri

fgetchar, bir hata veya dosya `EOF` sonu belirtmek için **int** olarak okunan karakteri döndürür veya döndürür. ** \_** fgetwchar, bir [wint_t](../../c-runtime-library/standard-types.md)olarak, bir hata veya dosya sonunu `WEOF` belirtmek için okunan veya döndüren karaktere karşılık gelen geniş karakter olarak döndürür. ** \_** Her iki işlev için de hata ile dosya sonu koşulunu ayırt etmek için **feof** veya **ferror** kullanın.

## <a name="remarks"></a>Açıklamalar

Bu işlevler **stdin**tek bir karakter okuyun. İşlev daha sonra ilişkili dosya işaretçisini (tanımlanmışsa) bir sonraki karaktere işaret etmek için artımlar. Akış dosyanın sonundaysa, akış için dosya sonu göstergesi ayarlanır.

**_fgetchar'a** `fgetc( stdin )`eşdeğerdir. Aynı zamanda **getchar**eşdeğerdir , ama sadece bir işlev olarak uygulanan, yerine bir işlev ve bir makro olarak. **_fgetwchar** **_fgetchar**geniş karakterli sürümüdür.

Bu işlevler ANSI standardı ile uyumlu değildir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_fgettchar**|**_fgetchar**|**_fgetchar**|**_fgetwchar**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fgetchar**|\<stdio.h>|
|**_fgetwchar**|\<stdio.h> \<veya wchar.h>|

Konsol, Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Konsolla ilişkili standart akış kolları**stdin,** **stdout**ve **stderr,** C çalışma zamanı işlevleri UWP uygulamalarında kullanamadan önce yeniden yönlendirilmelidir. Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
