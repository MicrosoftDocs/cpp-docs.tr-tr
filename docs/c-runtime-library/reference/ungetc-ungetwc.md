---
title: ungetc, ungetwc
ms.date: 11/04/2016
apiname:
- ungetwc
- ungetc
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
- _ungettc
- ungetwc
- ungetc
helpviewer_keywords:
- ungetwc function
- ungettc function
- characters, pushing back onto stream
- _ungettc function
- ungetc function
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
ms.openlocfilehash: c504540f8fbbe14961fa051bb93ebef350c2c1da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155439"
---
# <a name="ungetc-ungetwc"></a>ungetc, ungetwc

Karakteri akışa geri iter.

## <a name="syntax"></a>Sözdizimi

```C
int ungetc(
   int c,
   FILE *stream
);
wint_t ungetwc(
   wint_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
İtilecek karakter.

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı, bu işlevlerin her biri karakteri bağımsız değişkenini döndürür, *c*. Varsa *c* geri itilemiyorsa veya herhangi bir karakter okunmamışsa, Giriş akışı değiştirilmez ve **ungetc** döndürür **EOF**; **ungetwc** döndürür **WEOF**. Varsa *stream* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **EOF** veya **WEOF** döndürülür ve **errno** ayarlanır **EINVAL**.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Ungetc** işlevi karakter gönderim *c* geri *stream* ve dosya sonu göstergesini temizler. Akışın okunmak için açık olmalıdır. İlgili bir sonraki okuma işlemi *stream* ile başlayan *c*. Denemek **EOF** kullanarak akış üzerine **ungetc** göz ardı edilir.

Göre akışa yerleştirilen karakterler **ungetc** çağrılırsa silinebilir **fflush**, [fseek](fseek-fseeki64.md), **fsetpos**, veya [GeriSar](rewind.md) karakter akıştan okunmadan önce çağrılır. Dosya Konum göstergesi karakterler geri itilmeden önceki değerine sahip olacaktır. Akışa karşılık gelen dış depo değişmeden kalır. Başarılı bir üzerinde **ungetc** dosya konumu göstergesi metin akışına yönelik çağrı belirtilmeyen tüm geri itilen karakterler okunana veya atıldı. Her başarılı **ungetc** dosya konumu göstergesi ikili akışa karşı çağrı azaltılır; değer bir çağrıdan önce 0 değerini ise ve çağrının ardından tanımsızdır.

Sonuçların tahmin edilemeyeceğine varsa **ungetc** bir okuma veya dosyada konumlanma işlemi iki çağrı arasında olmadan iki kez çağrılır. Çağrısı yapıldıktan sonra **fscanf**, çağrı **ungetc** başka bir okuma işlemi başarısız olabilir (gibi **getc**) gerçekleştirildi. Bunun nedeni, **fscanf** kendi kendini çağıran **ungetc**.

**ungetwc** geniş karakterli sürümüdür **ungetc**. Ancak, her üzerinde başarılı **ungetwc** çağrısı bir metin veya ikili akışa dosya konumu göstergesi değeri belirtilmeyen tüm geri itilen karakterler okunana veya atılana kadar.

Bu işlevler, iş parçacığı bakımından güvenlidir ve yürütme sırasında hassas verileri kilitleyin. Kilitleme yapılmayan bir sürüm için bkz. [_ungetc_nolock, _ungetwc_nolock](ungetc-nolock-ungetwc-nolock.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc**|**ungetc**|**ungetc**|**ungetwc**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ungetc**|\<stdio.h >|
|**ungetwc**|\<stdio.h > veya \<wchar.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsolları ile ilişkili standart akış işleyicileri **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_ungetc.c
// This program first converts a character
// representation of an unsigned integer to an integer. If
// the program encounters a character that is not a digit,
// the program uses ungetc to replace it in the  stream.
//

#include <stdio.h>
#include <ctype.h>

int main( void )
{
   int ch;
   int result = 0;

   // Read in and convert number:
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )
      result = result * 10 + ch - '0';    // Use digit.
   if( ch != EOF )
      ungetc( ch, stdin );                // Put nondigit back.
   printf( "Number = %d\nNext character in stream = '%c'",
            result, getchar() );
}
```

```Output

      521aNumber = 521
Next character in stream = 'a'
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
