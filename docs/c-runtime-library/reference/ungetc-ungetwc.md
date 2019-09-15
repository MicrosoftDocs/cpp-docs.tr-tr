---
title: ungetc, ungetwc
ms.date: 11/04/2016
api_name:
- ungetwc
- ungetc
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
ms.openlocfilehash: f3b6c6ed3fe8ff5976afa1da2ed437e25c923b99
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957413"
---
# <a name="ungetc-ungetwc"></a>ungetc, ungetwc

Bir karakteri akışa geri gönderir.

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
Gönderilecek karakter.

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevlerin her biri *c*karakter bağımsız değişkenini döndürür. *C* yeniden gönderilemezse veya hiçbir karakter okunmunup, giriş akışı değiştirilmez ve **ungetc** , **EOF**döndürür; **ungetwc** **, weof**döndürür. *Stream* **null**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **EOF** veya **weof** döndürülür ve **errno** , **EINVAL**olarak ayarlanır.

Bu ve diğer hata kodları hakkında bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Ungetc** işlevi, *c* karakterini *akışa* geri gönderir ve dosya sonu göstergesini temizler. Akış, okuma için açık olmalıdır. *Akışta* sonraki bir okuma işlemi *c*ile başlar. **Ungetc** kullanarak akışa **EOF** gönderme girişimi yoksayılır.

Karakteri akıştan okunmadan önce **fflush**, [fseek](fseek-fseeki64.md), **fsetpos**veya [geri sarma](rewind.md) çağrılırsa **ungetc** tarafından akışa yerleştirilmiş karakterler silinebilir. Dosya konumu göstergesi, karakterlerin geri itilene kadar olan değere sahip olacaktır. Akışa karşılık gelen dış depolama alanı değiştirilmez. Bir metin akışına karşı başarılı bir **ungetc** çağrısında, geri gönderilen tüm karakterler okunana veya iptal edilene kadar dosya konumu göstergesi belirtilmemiş. Her başarılı **ungetc** çağrısının bir ikili akışa karşı, dosya konumu göstergesi azaltılır; bir çağrıdan önce değeri 0 ise, çağrıdan sonra değer tanımsız olur.

**Ungetc** , iki çağrı arasında okuma veya dosya konumlandırma işlemi olmadan iki kez çağrılırsa, sonuçlar öngörülemez. **Fscanf**çağrısından sonra, başka bir okuma işlemi ( **getc**gibi) gerçekleştirilmediği sürece **ungetc** çağrısı başarısız olabilir. Bunun nedeni **fscanf** 'in kendisinin **ungetc**'yi çağırması.

**ungetwc** , **ungetc**öğesinin geniş karakterli bir sürümüdür. Ancak, bir metin veya ikili akışa karşı başarılı bir şekilde gerçekleştirilen her bir **getwc** çağrısında, geri gönderilen tüm karakterler okunana veya iptal edilene kadar dosya konumu göstergesinin değeri belirtilmemiş olur.

Bu işlevler iş parçacığı açısından güvenlidir ve yürütme sırasında hassas verileri kilitler. Kilitleme dışı bir sürüm için bkz. [_ungetc_nolock, _ungetwc_nolock](ungetc-nolock-ungetwc-nolock.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc**|**ungetc**|**ungetc**|**ungetwc**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ungetc**|\<stdio. h >|
|**ungetwc**|\<stdio. h > veya \<wchar. h >|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Console, **STDIN**, **stdout**ve **stderr**Ile ilişkili standart akış TUTAMAÇLARı, C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
