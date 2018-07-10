---
title: putchar, putwchar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- putchar function
- _puttchar function
- characters, writing
- standard output, writing to
- putwchar function
ms.assetid: 93657c7f-cca1-4032-8e3a-cd6ab6193748
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7602ca44d6f8ec8197d1ebc61b4ef1d0847133f6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404629"
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

Yazılan karakteri döndürür. Bir hata veya dosya sonu koşulu belirtmek için **putc** ve **putchar** dönüş ** EOF`; **putwc` ve **putwchar** dönmek **WEOF**. Tüm dört yordamları için kullanmak [ferror](ferror.md) veya [feof](feof.md) bir hata veya dosya sonu için denetlemek için. Null işaretçinin aktarılırsa *akış*, açıklandığı gibi geçersiz bir parametre özel durum, bu işlevler üret [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Döndürmeleri yürütme devam etmek için izin verilip verilmediğini, **EOF** veya **WEOF** ve **errno** için **EINVAL**.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

**Putc** yordamı Yazar tek karakter *c* çıktısına *akış* geçerli konumundaki. Herhangi bir tamsayı için geçirilebilir **putc**, ancak yalnızca alt 8 bit yazılır. **Putchar** yordamdır aynı **putc (** * c ***, stdout)**. Okuma hatası oluşursa, her yordam için akış için hata göstergesi ayarlanır. **putc** ve **putchar** benzer **fputc** ve **_fputchar**, sırasıyla hem işlevleri de makroları olarak uygulanan ancak (bkz: [ İşlevlerle makrolar arasında seçim](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)). **putwc** ve **putwchar** joker karakter sürümleri **putc** ve **putchar**sırasıyla.

Sürümleriyle **_nolock** soneki, diğer iş parçacıkları tarafından girişime korunmayan dışında aynıdır. Bunlar başka bir iş parçacığı kilitleme zahmetine değil olduğundan daha hızlı olabilir. Bu işlevler yalnızca iş parçacığı bağlamları tek iş parçacıklı uygulamalar veya arama kapsamı zaten iş parçacığı yalıtım işleme olduğu gibi kullanın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_puttchar**|**putchar**|**putchar**|**putwchar**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**putchar**|\<stdio.h >|
|**putwchar**|\<stdio.h > veya \<wchar.h >|

Konsol Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsol ile ilişkili standart akış tanıtıcıları **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri UWP uygulamalarında kullanabilmek için önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
