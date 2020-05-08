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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 406ce7d8befd1d9e9e6a065f2549bacf46d2fd6e
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82915976"
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

*,*<br/>
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

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc**|**ungetc**|**ungetc**|**ungetwc**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ungetc**|\<stdio. h>|
|**ungetwc**|\<stdio. h> veya \<wchar. h>|

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
