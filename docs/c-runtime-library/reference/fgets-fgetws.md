---
title: fgets, fgetws
ms.date: 4/2/2020
api_name:
- fgets
- fgetws
- _o_fgets
- _o_fgetws
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
- _fgetts
- fgetws
- fgets
helpviewer_keywords:
- _fgetts function
- streams, getting strings from
- streams, reading from
- fgets function
- fgetws function
- fgetts function
ms.assetid: ad549bb5-df98-4ccd-a53f-95114e60c4fc
ms.openlocfilehash: a1120529157801aac5cf1c4fd61f844fde443bed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346861"
---
# <a name="fgets-fgetws"></a>fgets, fgetws

Bir akıştan bir dize alın.

## <a name="syntax"></a>Sözdizimi

```C
char *fgets(
   char *str,
   int numChars,
   FILE *stream
);
wchar_t *fgetws(
   wchar_t *str,
   int numChars,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Veriler için depolama konumu.

*numChars*<br/>
Okunacak maksimum karakter sayısı.

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri *str döndürür.* **NULL** bir hata veya dosya sonu koşulunu belirtmek için döndürülür. Bir hatanın oluşup oluşmadığını belirlemek için **feof** veya **ferror** kullanın. *Str* veya *akış* null işaretçisi ise veya *numChars* sıfırdan az veya eşitse, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev **NULL**döndürür.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

**Fgets** işlevi giriş *akışı* bağımsız değişkeninden bir dize okur ve *str*depolar. **fgets,** geçerli akış konumundan ilk yeni çizgi karakterine, akışın sonuna kadar veya okunan karakter sayısı *numChars'a* eşit olana kadar karakterleri okur - 1, hangisi önce gelirse. *Str'de* depolanan sonuç null bir karakterle eklenir. Yeni satır karakteri, okunursa, dize ye dahil edilir.

**fgetws** **fgets**geniş karakterli bir sürümüdür.

**fgetws,** *akış* metin modunda mı yoksa ikili modda mı açıldığına göre geniş karakterli bağımsız *değişkeni* çok bayt lı bir dize veya geniş karakter lisi olarak okur. Unicode ve multibayt akış-I/O metin ve ikili modları kullanma hakkında daha fazla bilgi için Metin [ve İkili Modları Metin ve İkili Modlarda Metin ve İkili Modlar'da Metin ve İkili Modlar Dosya I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [Unicode Stream G/Ç'ye](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgetts**|**fgets**|**fgets**|**fgetws**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fgets**|\<stdio.h>|
|**fgetws**|\<stdio.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_fgets.c
// This program uses fgets to display
// the first line from a file.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char line[100];

   if( fopen_s( &stream, "crt_fgets.txt", "r" ) == 0 )
   {
      if( fgets( line, 100, stream ) == NULL)
         printf( "fgets error\numChars" );
      else
         printf( "%s", line);
      fclose( stream );
   }
}
```

### <a name="input-crt_fgetstxt"></a>Giriş: crt_fgets.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıktı

```Output
Line one.
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
