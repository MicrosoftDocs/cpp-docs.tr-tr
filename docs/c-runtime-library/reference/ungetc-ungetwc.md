---
title: ungetc, ungetwc
ms.date: 4/2/2020
api_name:
- ungetwc
- ungetc
- _o_ungetc
- _o_ungetwc
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
ms.openlocfilehash: 484af7b72f860a8a9d12cf0b62444871caad4675
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361290"
---
# <a name="ungetc-ungetwc"></a>ungetc, ungetwc

Bir karakteri akışına geri iter.

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

*C*<br/>
Karakter itilecek.

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevlerin her biri karakter bağımsız *değişkeni c*döndürür. *C* geri itilemezse veya karakter okunmamışsa, giriş akışı değişmez ve **ungetc** **EOF**döndürür; **ungetwc** **WEOF**döner. *Akış* **NULL**ise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **EOF** veya **WEOF** döndürülür ve **errno** **EINVAL**olarak ayarlanır.

Bu ve diğer hata kodları hakkında bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**Ungetc** işlevi *c* karakterini *yeniden akışa* iter ve dosya sonu göstergesini temizler. Akış okumak için açık olmalıdır. *Akışta* sonraki bir okuma işlemi *c*ile başlar. **EOF'yi** **ungetc** kullanarak akışa itme girişimi göz ardı edilir.

Akışa **ungetc** tarafından yerleştirilen karakterler, **fflush**, [fseek](fseek-fseeki64.md), **fsetpos**, veya [geri sarma](rewind.md) karakter akışından okunmadan önce çağrılır silebilir. Dosya konumu göstergesi, karakterler geri itilmeden önceki değerine sahip olacaktır. Akışa karşılık gelen dış depolama alanı değişmez. Metin akışına karşı başarılı bir **çağrıda,** dosya konumu göstergesi tüm itilen karakterler okunana veya atılıncaya kadar belirtilmemiş olur. İkili akışa karşı her başarılı **ungetc** çağrısında, dosya konumu göstergesi karara bağlanmış; aramadan önce değeri 0 ise, değer aramadan sonra tanımsızdır.

**Ungetc** iki arama arasında okuma veya dosya konumlandırma işlemi olmadan iki kez çağrılırsa sonuçlar tahmin edilemez. **FScanf'a**yapılan bir çağrıdan sonra, başka bir okuma işlemi **(getc**gibi) yapılmadığı sürece **ungetc'e** yapılan bir çağrı başarısız olabilir. **Fscanf** kendisi **ungetc**çağırır olmasıdır.

**ungetwc** **ungetc**geniş karakterli bir sürümüdür. Ancak, bir metin veya ikili akışa karşı her başarılı **ungetwc** çağrısında, dosya konumu göstergesinin değeri tüm itilen karakterler okunana veya atılıncaya kadar belirtilmemiştir.

Bu işlevler iş parçacığı güvenlidir ve yürütme sırasında hassas verileri kilitler. Kilitsiz bir sürüm için [_ungetc_nolock _ungetwc_nolock](ungetc-nolock-ungetwc-nolock.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc**|**Ungetc**|**Ungetc**|**ungetwc**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Ungetc**|\<stdio.h>|
|**ungetwc**|\<stdio.h> \<veya wchar.h>|

Konsol, Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Konsol, **stdin,** **stdout**ve **stderr**ile ilişkili standart akış kolları, C çalışma zamanı işlevleri UWP uygulamalarında bunları kullanamadan önce yönlendirilmelidir. Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
