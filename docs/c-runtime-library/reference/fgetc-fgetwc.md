---
title: fgetc, fgetwc
ms.date: 11/04/2016
api_name:
- fgetwc
- fgetc
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
- _fgettc
- fgetwc
- fgetc
helpviewer_keywords:
- fgettc function
- characters, reading
- _fgettc function
- fgetc function
- streams, reading characters from
- reading characters from streams
- fgetwc function
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
ms.openlocfilehash: 92f44c65802f3baed37078574577bf108bbcd09a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940886"
---
# <a name="fgetc-fgetwc"></a>fgetc, fgetwc

Akıştan bir karakter okur.

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

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**fgetc** , bir **int** olarak okunan karakteri döndürür veya bir hata ya da dosya sonunu göstermek için **EOF** döndürür. **fgetwc** , bir [wint_t](../../c-runtime-library/standard-types.md)olarak, bir hata veya dosya sonunu göstermek için Read veya character karakteriyle karşılık gelen geniş **karakter döndürür.** Her iki işlev için de bir hata ve dosya sonu koşulu arasında ayrım yapmak için **feof** veya **ferror** kullanın. Bir okuma hatası oluşursa, akışın hata göstergesi ayarlanır. *Stream* **null**ise, **fgetc** ve **fgetwc** [parametresi, parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve **EOF**döndürecek şekilde ayarlanır.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, *Stream*ile ilişkili dosyanın geçerli konumundan tek bir karakter okur. İşlev daha sonra, ilişkili dosya işaretçisini (tanımlanmışsa) sonraki karakteri işaret etmek için artırır. Akış dosyanın sonunda ise, akış için dosya sonu göstergesi ayarlanır.

**fgetc** , **getc**ile eşdeğerdir, ancak bir işlev ve makro olarak değil, yalnızca işlev olarak uygulanır.

**fgetwc** , **fgetc**; öğesinin geniş karakterli sürümüdür *akış* metin modunda veya ikili modda açılıp açılmayacağı gibi çok baytlı bir karakter veya geniş karakter olarak **c** 'yi okur.

**_Nolock** sonekine sahip sürümler, diğer iş parçacıkları tarafından girişime karşı korunmamaları dışında aynıdır.

Metin ve ikili modlarda geniş karakter ve çok baytlı karakterler işleme hakkında daha fazla bilgi için bkz. [metin ve Ikili modlarda Unicode akışı g/ç](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgettc**|**fgetc**|**fgetc**|**fgetwc**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fgetc**|\<stdio. h >|
|**fgetwc**|\<stdio. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

## <a name="input-crt_fgetctxt"></a>Giriş: crt_fgetc. txt

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
