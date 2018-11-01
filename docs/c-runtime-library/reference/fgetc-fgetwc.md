---
title: fgetc, fgetwc
ms.date: 11/04/2016
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
helpviewer_keywords:
- fgettc function
- characters, reading
- _fgettc function
- fgetc function
- streams, reading characters from
- reading characters from streams
- fgetwc function
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
ms.openlocfilehash: a853a46fc43106c9ea57be84b37fb46a18041ba8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639929"
---
# <a name="fgetc-fgetwc"></a>fgetc, fgetwc

Bir karakter, bir akıştan okuyun.

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

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**fgetc** olarak okuma karakteri döndürür bir **int** veya döndürür **EOF** bir hata veya dosya sonunu belirtmek için. **fgetwc** döndürür, olarak bir [wint_t](../../c-runtime-library/standard-types.md), döndürür veya okuma karakterine karşılık gelen geniş karakter **WEOF** bir hata veya dosya sonunu belirtmek için. Her iki işlev için kullanmak **feof** veya **ferror** hata ve bir dosya sonu koşulunu ayırt etmek için. Okuma hatası oluşursa, akış için hata göstergesi ayarlanır. Varsa *stream* olduğu **NULL**, **fgetc** ve **fgetwc** açıklandığı gibi geçersiz parametre işleyicisini çağırır [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve dönüş **EOF**.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri ile ilişkili dosyayı geçerli konumundan tek bir karakter okur *stream*. İşlevi ardından ilgili dosya işaretleyicisini (tanımlıysa) sonraki karaktere işaret etmek üzere artırır. Akış dosya sonunda ise, akış için dosya sonu göstergesi ayarlanır.

**fgetc** eşdeğerdir **getc**, ancak bir işlev ve makro olarak değil, yalnızca işlev olarak uygulanır.

**fgetwc** öğesinin geniş karakterli sürümüdür **fgetc**; okuduğu **c** bir çok baytlı karakter veya geniş bir karakter olup olmadığına göre *stream* içinde açılır metin modunda veya İkili modda.

Sürümlerle **_nolock** soneki, bunlar başka iş parçacıklarının engellemelerinden korunmamaları hariç, aynıdır.

Geniş karakter ve çok baytlı karakter metin ve ikili modlarda işleme hakkında daha fazla bilgi için bkz. [metin ve ikili modlarda Unicode Stream g/ç](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgettc**|**fgetc**|**fgetc**|**fgetwc**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fgetc**|\<stdio.h >|
|**fgetwc**|\<stdio.h > veya \<wchar.h >|

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
