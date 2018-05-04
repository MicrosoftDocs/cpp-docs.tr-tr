---
title: fgetc, fgetwc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fgetwc
- fgetc
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
- _fgettc
- fgetwc
- fgetc
dev_langs:
- C++
helpviewer_keywords:
- fgettc function
- characters, reading
- _fgettc function
- fgetc function
- streams, reading characters from
- reading characters from streams
- fgetwc function
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f06c5c2f092932d97755a8f0cff63cde3a9682c6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fgetc-fgetwc"></a>fgetc, fgetwc

Bir karakterin üzerinden bir akış okuyun.

## <a name="syntax"></a>Sözdizimi

```C
int fgetc(
   FILE *stream
);
wint_t fgetwc(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Akış*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**fgetc** olarak okuma karakteri döndürür bir **int** veya verir **EOF** bir hata veya dosya sonu belirtmek için. **fgetwc** döndürür, olarak bir [wint_t](../../c-runtime-library/standard-types.md), okuma karakterine karşılık gelen veya verir geniş karakter **WEOF** bir hata veya dosya sonu belirtmek için. Her iki işlevlerini kullanmak **feof** veya **ferror** hata bir dosya sonu durumu arasında ayrım yapmak için. Okuma hatası oluşursa, akış için hata göstergesi ayarlanır. Varsa *akış* olan **NULL**, **fgetc** ve **fgetwc** açıklandığı gibi geçersiz parametre işleyicisi çağırma [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve geri dönüp **EOF**.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri tek bir karakter ile ilişkili dosya geçerli konumunu okur *akış*. İşlev sonra ilişkili dosya işaretçisini (tanımlıysa) sonraki karaktere işaret edecek şekilde artırır. Akış dosya sonu ise dosya sonu gösterge akış için ayarlanır.

**fgetc** eşdeğerdir **getc**, ancak bir işlev ve bir makro değil, yalnızca bir işlevi olarak uygulanır.

**fgetwc** geniş karakter sürümü **fgetc**; bunu okuyan **c** birden çok baytlı karakter veya mi göre geniş karakter olarak *akış* açılır metin modu veya ikili modu.

Sürümleriyle **_nolock** soneki, diğer iş parçacıkları tarafından girişime korunmayan dışında aynıdır.

Geniş karakterler ve birden çok baytlı karakterler metin ve ikili modlarda işleme hakkında daha fazla bilgi için bkz: [metin ve ikili modlarda Unicode akışı g/ç](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgettc**|**fgetc**|**fgetc**|**fgetwc**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fgetc**|\<stdio.h >|
|**fgetwc**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fgetc.c
// This program uses getc to read the first
// 80 input characters (or until the end of input)
// and place them into a string named buffer.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   char buffer[81];
   int  i, ch;

   // Open file to read line from:
   fopen_s( &stream, "crt_fgetc.txt", "r" );
   if( stream == NULL )
      exit( 0 );

   // Read in first 80 characters and place them in "buffer":
   ch = fgetc( stream );
   for( i=0; (i < 80 ) && ( feof( stream ) == 0 ); i++ )
   {
      buffer[i] = (char)ch;
      ch = fgetc( stream );
   }

   // Add null to end string
   buffer[i] = '\0';
   printf( "%s\n", buffer );
   fclose( stream );
}
```

## <a name="input-crtfgetctxt"></a>Giriş: crt_fgetc.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıkış

```Output
Line one.
Line two.
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
