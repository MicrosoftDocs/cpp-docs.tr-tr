---
description: 'Daha fazla bilgi edinin: printf, _printf_l, wprintf, _wprintf_l'
title: printf, _printf_l, wprintf, _wprintf_l
ms.date: 11/04/2016
api_name:
- _printf_l
- wprintf
- _wprintf_l
- printf
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- printf
- _tprintf
- wprintf
helpviewer_keywords:
- printf function
- printf_l function
- tprintf_l function
- tprintf function
- _printf_l function
- wprintf function
- writing to console
- wprintf_l function
- _tprintf_l function
- _wprintf_l function
- _tprintf function
- printf function, format specification fields
- printf function, using
- formatted text [C++]
ms.assetid: 77a854ae-5b48-4865-89f4-f2dc5cf80f52
ms.openlocfilehash: cd38713b4646536fb2ee5186810fd7630478743f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252837"
---
# <a name="printf-_printf_l-wprintf-_wprintf_l"></a>printf, _printf_l, wprintf, _wprintf_l

Biçimli çıktıyı standart çıkış akışına yazdırır. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](printf-s-printf-s-l-wprintf-s-wprintf-s-l.md).

## <a name="syntax"></a>Sözdizimi

```C
int printf(
   const char *format [,
   argument]...
);
int _printf_l(
   const char *format,
   locale_t locale [,
   argument]...
);
int wprintf(
   const wchar_t *format [,
   argument]...
);
int _wprintf_l(
   const wchar_t *format,
   locale_t locale [,
   argument]...
);
```

### <a name="parameters"></a>Parametreler

*formatını*<br/>
Biçim denetimi.

*değişkendir*<br/>
İsteğe bağlı bağımsız değişkenler.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa yazdırılan karakter sayısını veya negatif bir değer döndürür. *Biçim* **null** ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa işlev-1 döndürür ve **errno** öğesini **EINVAL** olarak ayarlar. *Bağımsız değişkende* **EOF** (0xFFFF) ile karşılaşılırsa, işlev-1 döndürür.

**Errno** ve hata kodları hakkında bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Printf** işlevi, standart çıkış akışına, **stdout** öğesine bir dizi karakter ve değer yazar ve yazdırır. Bağımsız değişkenler *Biçim* dizesini izleyemiyorsa, *Biçim* dizesinin bağımsız değişkenlerin çıkış biçimini belirten belirtimleri içermesi gerekir. **printf** ve [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md) aynı şekilde davranır. Bu, **printf** çıkışı **Dosya** türü hedefi yerine **stdout** 'a yazar.

**wprintf** , **printf** öğesinin geniş karakterli bir sürümüdür; *Biçim* geniş karakterli bir dizedir. Akış ANSI modunda açılırsa **wprintf** ve **printf** aynı şekilde davranır. **printf** Şu anda bir UNICODE akışına çıktıyı desteklemez.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_unicode tanımlı|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tprintf**|**printf**|**printf**|**wprintf**|

*Biçim* bağımsız değişkeni, normal karakterlerden, kaçış dizilerinden ve (bağımsız değişkenlerin *biçimi* ise) biçim belirtimlerinden oluşur. Sıradan karakterler ve kaçış dizileri, kendi görünümleri sırasıyla **stdout** 'a kopyalanır. Örneğin, satır:

```C
printf("Line one\n\t\tLine two\n");
```

çıktıyı üretir:

```Output
Line one
        Line two
```

[Biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) her zaman yüzde işaretiyle () başlar **%** ve soldan sağa doğru okunurdur. **Printf** ilk biçim belirtimiyle karşılaştığında (varsa), *Biçim* sonrasında ilk bağımsız değişkenin değerini dönüştürür ve buna uygun şekilde çıkış yapar. İkinci biçim belirtimi ikinci bağımsız değişkenin dönüştürülmesine ve çıktısına ve bu şekilde devam etmesine neden olur. Biçim belirtimlerinden daha fazla bağımsız değişken varsa, ek bağımsız değişkenler yoksayılır. Tüm biçim belirtimleri için yeterli bağımsız değişken yoksa sonuçlar tanımsızdır.

> [!IMPORTANT]
> *Biçimin* Kullanıcı tanımlı bir dize olmadığından emin olun.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tprintf**|**printf**|**printf**|**wprintf**|
|**_tprintf_l**|**_printf_l**|**_printf_l**|**_wprintf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**printf**, **_printf_l**|\<stdio.h>|
|**wprintf**, **_wprintf_l**|\<stdio.h> veya \<wchar.h>|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Console, **STDIN**, **stdout** ve **stderr** Ile ilişkili standart akış TUTAMAÇLARı, C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

> [!IMPORTANT]
> Windows 10 sürüm 2004 (derleme 19041) ' den başlayarak, `printf` işlev ailesi, yuvarlama IÇIN ıeee 754 kurallarına göre tam olarak gösterilemeyen kayan nokta numaralarını yazdırır. Önceki Windows sürümlerinde, ' 5 ' ile biten tam olarak gösterilemeyen kayan noktalı sayılar her zaman yukarı yuvarlar. IEEE 754, en yakın çift basamağa ("Banker ' de yuvarlama" olarak da bilinir) yuvarlayabilmeleri gerektiğini belirtir. Örneğin, 1,5 ve 2,5 her ikisi de 2 ' ye yuvarlanmalıdır. 1,5, daha önce 2,5 2 ' ye yuvarlayacağından, 3 ' e yuvarlanacak. Bu değişiklik yalnızca tam olarak gösterilebilir tablo numaralarını etkiler. Örneğin, 2,35 (bellekte temsil edildiğinde, 2.35000000000000008 'e yaklaşmışsa), 2,4 ' e yuvarlamaya devam eder. Bu işlevler tarafından yapılan yuvarlama artık [fesetround](fegetround-fesetround2.md)tarafından ayarlanan kayan nokta yuvarlama moduna de uyar. Daha önce, yuvarlama FE_TONEAREST davranışı her zaman seçti. Bu değişiklik yalnızca Visual Studio 2019 sürüm 16,2 ve üzeri kullanılarak oluşturulan programları etkiler. Eski kayan nokta yuvarlama davranışını kullanmak için [legacy_stdio_float_rounding. obj](../link-options.md)ile bağlayın.

## <a name="example"></a>Örnek

```C
// crt_printf.c
// This program uses the printf and wprintf functions
// to produce formatted output.

#include <stdio.h>

int main( void )
{
   char     ch = 'h',
            *string = "computer";
   wchar_t  wch = L'w',
            *wstring = L"Unicode";
   int      count = -9234;
   double   fp = 251.7366;

   // Display integers
   printf( "Integer formats:\n"
           "   Decimal: %d  Justified: %.6d  "
           "Unsigned: %u\n",
           count, count, count, count );

   // Display decimals
   printf( "Decimal %d as:\n   Hex: %Xh  "
           "C hex: 0x%x  Octal: %o\n",
            count, count, count, count );

   // Display in different radixes
   printf( "Digits 10 equal:\n   Hex: %i  "
           "Octal: %i  Decimal: %i\n",
            0x10, 010, 10 );

   // Display characters
   printf("Characters in field (1):\n"
          "%10c%5hc%5C%5lc\n",
          ch, ch, wch, wch);
   wprintf(L"Characters in field (2):\n"
           L"%10C%5hc%5c%5lc\n",
           ch, ch, wch, wch);

   // Display strings
   printf("Strings in field (1):\n%25s\n"
          "%25.4hs\n   %S%25.3ls\n",
          string, string, wstring, wstring);
   wprintf(L"Strings in field (2):\n%25S\n"
           L"%25.4hs\n   %s%25.3ls\n",
           string, string, wstring, wstring);

   // Display real numbers
   printf("Real numbers:\n   %f %.2f %e %E\n",
          fp, fp, fp, fp );

   // Display pointer
   printf( "\nAddress as:   %p\n", &count);
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

Address as:   0012FF3C
```

## <a name="see-also"></a>Ayrıca bkz.

[Biçim belirtimi sözdizimi: printf ve wprintf Işlevleri](../format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vprintf Işlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
[_set_output_format](../../c-runtime-library/set-output-format.md)<br/>
