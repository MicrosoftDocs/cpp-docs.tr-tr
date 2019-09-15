---
title: _fgetchar, _fgetwchar
ms.date: 11/04/2016
api_name:
- _fgetchar
- _fgetwchar
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
ms.openlocfilehash: 90a97308b8c60776d52e58feb84c5398456f26d5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940871"
---
# <a name="_fgetchar-_fgetwchar"></a>_fgetchar, _fgetwchar

**STDIN**'den bir karakter okur.

## <a name="syntax"></a>Sözdizimi

```C
int _fgetchar( void );
wint_t _fgetwchar( void );
```

## <a name="return-value"></a>Dönüş Değeri

fgetchar, bir **int** olarak okunan karakteri döndürür veya bir `EOF` hata ya da dosya sonunu belirtmek için döndürür.  **\_** fgetwchar, bir hata ya [](../../c-runtime-library/standard-types.md)da dosya sonunu göstermek için Read veya döndürüyor `WEOF` karakterine karşılık gelen geniş karakter, wint_t olarak döndürülür.  **\_** Her iki işlev için de bir hata ve dosya sonu koşulu arasında ayrım yapmak için **feof** veya **ferror** kullanın.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, **stdin**'den tek bir karakter okur. İşlev daha sonra, ilişkili dosya işaretçisini (tanımlanmışsa) sonraki karakteri işaret etmek için artırır. Akış dosyanın sonunda ise, akış için dosya sonu göstergesi ayarlanır.

**_fgetchar** ile `fgetc( stdin )`eşdeğerdir. Ayrıca, **GetChar**öğesine eşdeğerdir, ancak bir işlev ve makro olarak değil, yalnızca işlev olarak uygulanır. **_fgetwchar** , **_fgetchar**öğesinin geniş karakterli sürümüdür.

Bu işlevler ANSI standardı ile uyumlu değildir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_fgettchar**|**_fgetchar**|**_fgetchar**|**_fgetwchar**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fgetchar**|\<stdio. h >|
|**_fgetwchar**|\<stdio. h > veya \<wchar. h >|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Bu konsol ile ilişkili standart akış tutamaçları (**stdin**, **stdout**ve **stderr**), C çalışma zamanı işlevlerinin bunları UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
