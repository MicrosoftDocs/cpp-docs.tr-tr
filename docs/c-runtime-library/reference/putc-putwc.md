---
title: putc, putwc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- putwc
- putc
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
- _puttc
- putwc
- putc
dev_langs:
- C++
helpviewer_keywords:
- streams, writing characters to
- characters, writing
- putwc function
- putc function
- _puttc function
- puttc function
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af5c6987f88238398a00e9da7f0d769f246ffc54
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211075"
---
# <a name="putc-putwc"></a>putc, putwc

Bir akışa bir karakter yazar.

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

*c*<br/>
Yazılacak karakter.

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Yazılan karakteri döndürür. Bir hata veya dosya sonu koşulu belirtmek için **putc** ve **putchar** dönüş ** EOF`; **putwc` ve **putwchar** dönüş **WEOF**. Tüm dört yordamları için kullanmak [ferror](ferror.md) veya [feof](feof.md) bir hata veya dosya sonunu denetlemek için. Geçirilen bir null işaretçi *stream*, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **EOF** veya **WEOF** ayarlayıp **errno** için **EINVAL**.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

**Putc** yordamı tek bir karakter Yazar *c* çıktısına *stream* geçerli konumunda. Herhangi bir tamsayı geçirilebilir **putc**, ancak yalnızca alt 8 bit yazılır. **Putchar** yordamı `putc( c, stdout )`. Her bir rutin için bir okuma hatası oluşursa, akış için hata göstergesi ayarlanır. **putc** ve **putchar** benzer **fputc** ve **_fputchar**sırasıyla işlev gerekse makro olarak uygulanır ancak (bkz [ İşlevlerle makrolar arasında seçim](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)). **putwc** ve **putwchar** geniş karakterli sürümleridir **putc** ve **putchar**sırasıyla. **putwc** ve **putc** akış ANSI modunda açıldığında aynı şekilde davranır. **putc** UNICODE akışına çıkış şu anda desteklemiyor.

Sürümlerle **_nolock** soneki, bunlar başka iş parçacıklarının engellemelerinden korunmamaları hariç, aynıdır. Daha fazla bilgi için **_putc_nolock, _putwc_nolock**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_puttc**|**putc**|**putc**|**putwc**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**putc**|\<stdio.h >|
|**putwc**|\<stdio.h > veya \<wchar.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsolları ile ilişkili standart akış işleyicileri **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

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

### <a name="output"></a>Çıkış

```Output
This is the line of output
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
