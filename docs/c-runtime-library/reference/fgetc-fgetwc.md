---
title: fgetc, fgetwc
ms.date: 4/2/2020
api_name:
- fgetwc
- fgetc
- _o_fgetc
- _o_fgetwc
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
ms.openlocfilehash: c1589c64127b47f4dd2a1147f2b4d549601db4fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347003"
---
# <a name="fgetc-fgetwc"></a>fgetc, fgetwc

Bir akışından bir karakter okuyun.

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

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**fgetc,** **int** olarak okunan karakteri döndürür veya dosya nın sonunu belirtmek için **EOF'yi** döndürür. **fgetwc,** bir [wint_t](../../c-runtime-library/standard-types.md)olarak, bir hata veya dosya sonu belirtmek için **WEOF** okumak veya döndürür karaktere karşılık gelen geniş karakter döndürür. Her iki işlev için de hata ile dosya sonu koşulunu ayırt etmek için **feof** veya **ferror** kullanın. Okuma hatası oluşursa, akış için hata göstergesi ayarlanır. *Akış* **NULL**ise, **fgetc** ve **fgetwc,** [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütme devam etmesine izin verilirse, bu işlevler **EINVAL** **için errno** ayarlayın ve **EOF**döndürün.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her *biri, akışla*ilişkili dosyanın geçerli konumundan tek bir karakter okur. İşlev daha sonra ilişkili dosya işaretçisini (tanımlanmışsa) bir sonraki karaktere işaret etmek için artımlar. Akış dosyanın sonundaysa, akış için dosya sonu göstergesi ayarlanır.

**fgetc** **getc**eşdeğerdir, ancak bir işlev ve makro olarak değil, sadece bir işlev olarak uygulanır.

**fgetwc** **fgetc**geniş karakterli versiyonudur; *akış* metin modunda mı yoksa ikili modda mı açıldığına göre **c'yi** çok bayt karakter veya geniş bir karakter olarak okur.

**_nolock** sonekli sürümler, diğer iş parçacıkları tarafından parazite karşı korunmayan sürümler dışında aynıdır.

Metin ve ikili modlarda geniş karakterleri ve çok bayt karakterleri işleme hakkında daha fazla bilgi için [Metin ve İkili Modlarda Unicode Stream G/Ç'ye](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgettc**|**fgetc**|**fgetc**|**fgetwc**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fgetc**|\<stdio.h>|
|**fgetwc**|\<stdio.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

## <a name="input-crt_fgetctxt"></a>Giriş: crt_fgetc.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıktı

```Output
Line one.
Line two.
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
