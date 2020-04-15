---
title: putc, putwc
ms.date: 4/2/2020
api_name:
- putwc
- putc
- _o_putc
- _o_putwc
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
- _puttc
- putwc
- putc
helpviewer_keywords:
- streams, writing characters to
- characters, writing
- putwc function
- putc function
- _puttc function
- puttc function
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
ms.openlocfilehash: 8809595c90c48976d9f28ffa659714f5b9d919c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338453"
---
# <a name="putc-putwc"></a>putc, putwc

Bir akışa karakter yazar.

## <a name="syntax"></a>Sözdizimi

```C
int putc(
   int c,
   FILE *stream
);
wint_t putwc(
   wchar_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Yazılacak karakter.

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Yazılan karakteri döndürür. Bir hata veya dosya sonu koşulu belirtmek için, **putc** ve **putchar** return **EOF;** **putwc** ve **putwchar** dönüş **WEOF**. Dört yordam için de, bir hata veya dosya sonu olup olup yok olup yok olup yok diye [ferror](ferror.md) veya [feof](feof.md) kullanın. *Akış*için null işaretçisi geçtiyse, Geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, bu işlevler **EOF** veya **WEOF** döndürecek ve **EINVAL** **için errno** ayarlayın.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

**Putc** yordamı, geçerli konumdaki çıkış *akışına* tek karakter *c* yazar. Herhangi bir toplamda **putc**geçirilebilir, ancak sadece alt 8 bit yazılır. **Putchar** rutin ilerki. `putc( c, stdout )` Her yordam için, bir okuma hatası oluşursa, akış için hata göstergesi ayarlanır. **putc** ve **putchar** **fputc** ve **_fputchar**benzer , sırasıyla, ancak işlevler ve makrolar olarak hem de uygulanır [(Bkz. İşlevler ve Makrolar Arasında Seçim](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)). **putwc** ve **putwchar** **putc** ve **putchar**geniş karakter sürümleri , sırasıyla. akış ANSI modunda açıldığında **putwc** ve **putc** aynı şekilde çalışır. **putc** şu anda bir UNICODE akışına çıktı yı desteklemiyor.

**_nolock** sonekli sürümler, diğer iş parçacıkları tarafından parazite karşı korunmayan sürümler dışında aynıdır. Daha fazla bilgi için **_putc_nolock _putwc_nolock.**

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_puttc**|**putc**|**putc**|**putwc**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**putc**|\<stdio.h>|
|**putwc**|\<stdio.h> \<veya wchar.h>|

Konsol, Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Konsol, **stdin,** **stdout**ve **stderr**ile ilişkili standart akış kolları, C çalışma zamanı işlevleri UWP uygulamalarında bunları kullanamadan önce yönlendirilmelidir. Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// crt_putc.c
/* This program uses putc to write buffer
* to a stream. If an error occurs, the program
* stops before writing the entire buffer.
*/

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char *p, buffer[] = "This is the line of output\n";
   int  ch;

   ch = 0;
   /* Make standard out the stream and write to it. */
   stream = stdout;
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )
      ch = putc( *p, stream );
}
```

### <a name="output"></a>Çıktı

```Output
This is the line of output
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
