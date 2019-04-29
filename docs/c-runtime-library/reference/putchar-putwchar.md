---
title: putchar, putwchar
ms.date: 11/04/2016
apiname:
- putchar
- putwchar
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
- putchar
- putwchar
- _puttchar
helpviewer_keywords:
- putchar function
- _puttchar function
- characters, writing
- standard output, writing to
- putwchar function
ms.assetid: 93657c7f-cca1-4032-8e3a-cd6ab6193748
ms.openlocfilehash: becee3d79f58ac018d1161c1af36e9a4646640bf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358001"
---
# <a name="putchar-putwchar"></a>putchar, putwchar

Bir karakter Yazar **stdout**.

## <a name="syntax"></a>Sözdizimi

```C
int putchar(
   int c
);
wint_t putwchar(
   wchar_t c
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Yazılacak karakter.

## <a name="return-value"></a>Dönüş Değeri

Yazılan karakteri döndürür. Bir hata veya dosya sonu koşulu belirtmek için **putc** ve **putchar** dönüş **EOF**; **putwc** ve **putwchar** dönüş **WEOF**. Tüm dört yordamları için kullanmak [ferror](ferror.md) veya [feof](feof.md) bir hata veya dosya sonunu denetlemek için. Geçirilen bir null işaretçi *stream*, açıklanan şekilde geçersiz parametre özel durum, bu işlevleri oluşturmak [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bunlar döndürür **EOF** veya **WEOF** ayarlayıp **errno** için **EINVAL**.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

**Putc** yordamı tek bir karakter Yazar *c* çıktısına *stream* geçerli konumunda. Herhangi bir tamsayı geçirilebilir **putc**, ancak yalnızca alt 8 bit yazılır. **Putchar** yordamı `putc( c, stdout )`. Her bir rutin için bir okuma hatası oluşursa, akış için hata göstergesi ayarlanır. **putc** ve **putchar** benzer **fputc** ve **_fputchar**sırasıyla işlev gerekse makro olarak uygulanır ancak (bkz [ İşlevlerle makrolar arasında seçim](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)). **putwc** ve **putwchar** geniş karakterli sürümleridir **putc** ve **putchar**sırasıyla.

Sürümlerle **_nolock** soneki, bunlar başka iş parçacıklarının engellemelerinden korunmamaları hariç, aynıdır. Bu yana bunlar diğer iş parçacıklarının kilitleme yüküne tabi olmadıklarından daha hızlı olabilirler. Bu işlevler yalnızca tek iş parçacıklı uygulamalar ve burada çağırma kapsamının iş parçacığı yalıtımını zaten işlediği gibi iş parçacığı bakımından güvenli bağlamlarda kullanın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_puttchar**|**putchar**|**putchar**|**putwchar**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**putchar**|\<stdio.h >|
|**putwchar**|\<stdio.h > veya \<wchar.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsolları ile ilişkili standart akış işleyicileri **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_putchar.c
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

   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )
      ch = putchar( *p );
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
