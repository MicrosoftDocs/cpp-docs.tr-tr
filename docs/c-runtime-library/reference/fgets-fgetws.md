---
title: fgets, fgetws
ms.date: 07/11/2018
api_name:
- fgets
- fgetws
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
ms.openlocfilehash: 3f68bee181ebb20eb7a0a2eaca02a72c4dc03616
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957406"
---
# <a name="fgets-fgetws"></a>fgets, fgetws

Akıştan bir dize alın.

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

*üstbilgisine*<br/>
Veriler için depolama konumu.

*numChars*<br/>
Okunacak maksimum karakter sayısı.

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri *Str*döndürür. Bir hata veya dosya sonu koşulu göstermek için **null** döndürülür. Bir hatanın oluşup oluşmadığını anlamak için **feof** veya **ferror** kullanın. *Str* veya *Stream* null bir Işaretçisiyse veya *NumChars* değeri sıfıra eşit veya daha küçükse, bu işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **null**değerini döndürür.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

**Fal** işlevi, giriş *akışı* bağımsız değişkeninden bir dizeyi okur ve *Str*içinde depolar. **fal** , geçerli akış konumundan, ilk yeni satır karakterini, akışın sonuna kadar veya okunan karakter sayısı *numchar* -1 ' e eşit olana kadar (hangisi önce gelirse) karakterleri okur. *Str* içinde depolanan sonuç bir null karakterle eklenir. Read ise yeni satır karakteri dizeye dahil edilir.

**fgetws** , **fal**'ın geniş karakterli bir sürümüdür.

**fgetws** , IP 'nin sırasıyla metin modunda veya ikili modda açılıp *açılmayacağı bir* çok baytlı karakter dizesi veya geniş karakterli *dize olarak geniş* karakterli bağımsız değişkeni okur. Unicode ve çok baytlı akışta metin ve ikili modlar kullanma hakkında daha fazla bilgi için bkz. metin ve ikili [mod dosyası g/](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ç ve [Unicode akış g/ç ve metin ve ikili modlar](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgetts**|**fal**|**fal**|**fgetws**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fal**|\<stdio. h >|
|**fgetws**|\<stdio. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

### <a name="input-crt_fgetstxt"></a>Giriş: crt_fgets. txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıkış

```Output
Line one.
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
