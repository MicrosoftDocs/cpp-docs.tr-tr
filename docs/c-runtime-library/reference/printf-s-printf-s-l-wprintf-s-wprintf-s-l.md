---
title: printf_s, _printf_s_l, wprintf_s, _wprintf_s_l
ms.date: 11/04/2016
apiname:
- _printf_s_l
- wprintf_s
- _wprintf_s_l
- printf_s
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
apitype: DLLExport
f1_keywords:
- wprintf_s
- printf_s
helpviewer_keywords:
- wprintf_s function
- tprintf_s function
- _tprintf_s function
- printf_s_l function
- printf_s function
- _printf_s_l function
- printf function, format specification fields
- printf function, using
- _tprintf_s_l function
- wprintf_s_l function
- formatted text [C++]
- tprintf_s_l function
- _wprintf_s_l function
ms.assetid: 044ebb2e-5cc1-445d-bb4c-f084b405615b
ms.openlocfilehash: 6b07fd90e0390d5c39bc8f5885f5744de20eeb79
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524189"
---
# <a name="printfs-printfsl-wprintfs-wprintfsl"></a>printf_s, _printf_s_l, wprintf_s, _wprintf_s_l

Baskı siparişi standart çıkış akışına biçimlendirilmiş. Bu sürümleri [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
int printf_s(
   const char *format [,
   argument]...
);
int _printf_s_l(
   const char *format,
   locale_t locale [,
   argument]...
);
int wprintf_s(
   const wchar_t *format [,
   argument]...
);
int _wprintf_s_l(
   const wchar_t *format,
   locale_t locale [,
   argument]...
);
```

### <a name="parameters"></a>Parametreler

*Biçim*<br/>
Biçim Denetimi.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa yazdırılan karakter veya negatif bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Printf_s** işlevi biçimlendirir ve bir dizi karakter ve değerlerini standart çıkış akışına yazdırır **stdout**. Bağımsız değişkenler izlerseniz *biçimi* dize *biçimi* dizesi bağımsız değişkenler için çıkış biçimini belirleyen belirtimler içermelidir.

Arasındaki temel fark **printf_s** ve **printf** olan **printf_s** geçerli biçimlendirme karakterleri için biçim dizesi ise denetler **printf**  yalnızca biçim dizesinin bir null işaretçi olup olmadığını denetler. Ya da denetim de başarısız olursa, bir geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Devam etmek için işlev -1 döndürür ve kümeleri yürütülmesine izin veriliyorsa **errno** için **EINVAL**.

Hakkında bilgi için **errno** ve hata kodları [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**printf_s** ve **fprintf_s** aynı şekilde davranır **printf_s** çıktıları **stdout** türündebirhedefyerine**Dosya**. Daha fazla bilgi için [fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md).

**wprintf_s** geniş karakterli sürümüdür **printf_s**; *biçimi* geniş karakterli bir dizedir. **wprintf_s** ve **printf_s** akış ANSI modunda açıldığında aynı şekilde davranır. **printf_s** UNICODE akışına çıkış şu anda desteklemiyor.

Sahip bu işlevlerin sürümleri **_l** sonekine, geçerli iş parçacığı yerel ayarı yerine iletilen yerel ayar parametresini kullanmalarıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tprintf_s**|**printf_s**|**printf_s**|**wprintf_s**|
|**_tprintf_s_l**|**_printf_s_l**|**_printf_s_l**|**_wprintf_s_l**|

*Biçimi* bağımsız değişkeni çıkış sıraları sıradan karakterlerden oluşur ve (geliyorsa *biçimi*) biçimlendirir. Sıradan karakterler ve kaçış dizileri kopyalanır **stdout** görünme sırasına göre. Örneğin, satır

```C
printf_s("Line one\n\t\tLine two\n");
```

çıktıyı üretir

```Output
Line one
        Line two
```

[Biçim belirtimlerinden](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) her zaman yüzde işaretiyle başlar (**%**) ve soldan sağa doğru okunur. Zaman **printf_s** karşılaştığında ilk biçim belirtimiyle (varsa), sonra ilk bağımsız değişkenin değeri dönüştürür *biçimi* ve buna göre çıkarır. İkinci biçim belirtimi dönüştürülür ve çıktı, ikinci bağımsız değişkenin neden olur ve benzeri. Biçim belirtimleri sayısından daha fazla bağımsız değişken varsa, ek bağımsız değişkenler yoksayılır. Tüm biçim belirtimleri için yeterli bağımsız değişken varsa sonuçlar tanımsızdır.

> [!IMPORTANT]
> Emin *biçimi* kullanıcı tanımlı bir dize değil.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**printf_s**, **_printf_s_l**|\<stdio.h >|
|**wprintf_s**, **_wprintf_s_l**|\<stdio.h > veya \<wchar.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsolları ile ilişkili standart akış işleyicileri **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_printf_s.c
/* This program uses the printf_s and wprintf_s functions
* to produce formatted output.
*/

#include <stdio.h>

int main( void )
{
   char   ch = 'h', *string = "computer";
   int    count = -9234;
   double fp = 251.7366;
   wchar_t wch = L'w', *wstring = L"Unicode";

   /* Display integers. */
   printf_s( "Integer formats:\n"
           "   Decimal: %d  Justified: %.6d  Unsigned: %u\n",
           count, count, count );

   printf_s( "Decimal %d as:\n   Hex: %Xh  C hex: 0x%x  Octal: %o\n",
            count, count, count, count );

   /* Display in different radixes. */
   printf_s( "Digits 10 equal:\n   Hex: %i  Octal: %i  Decimal: %i\n",
            0x10, 010, 10 );

   /* Display characters. */

   printf_s("Characters in field (1):\n%10c%5hc%5C%5lc\n", ch, ch, wch, wch);
   wprintf_s(L"Characters in field (2):\n%10C%5hc%5c%5lc\n", ch, ch, wch, wch);

   /* Display strings. */

   printf_s("Strings in field (1):\n%25s\n%25.4hs\n   %S%25.3ls\n",
   string, string, wstring, wstring);
   wprintf_s(L"Strings in field (2):\n%25S\n%25.4hs\n   %s%25.3ls\n",
       string, string, wstring, wstring);

   /* Display real numbers. */
   printf_s( "Real numbers:\n   %f %.2f %e %E\n", fp, fp, fp, fp );

   /* Display pointer. */
   printf_s( "\nAddress as:   %p\n", &count);

}
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
Integer formats:
   Decimal: -9234  Justified: -009234  Unsigned: 4294958062
Decimal -9234 as:
   Hex: FFFFDBEEh  C hex: 0xffffdbee  Octal: 37777755756
Digits 10 equal:
   Hex: 16  Octal: 8  Decimal: 10
Characters in field (1):
         h    h    w    w
Characters in field (2):
         h    h    w    w
Strings in field (1):
                 computer
                     comp
   Unicode                      Uni
Strings in field (2):
                 computer
                     comp
   Unicode                      Uni
Real numbers:
   251.736600 251.74 2.517366e+002 2.517366E+002

Address as:   0012FF78
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
