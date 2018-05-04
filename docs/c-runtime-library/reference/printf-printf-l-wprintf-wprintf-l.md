---
title: Printf, _printf_l, wprintf, _wprintf_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _printf_l
- wprintf
- _wprintf_l
- printf
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
- printf
- _tprintf
- wprintf
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e66c185a6ee56e4a82a98e62d8d2c7d8167399e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="printf-printfl-wprintf-wprintfl"></a>printf, _printf_l, wprintf, _wprintf_l

Biçimlendirilmiş çıkışı için standart çıktı akışı yazdırır. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](printf-s-printf-s-l-wprintf-s-wprintf-s-l.md).

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

*Biçimi*<br/>
Denetim biçimlendirin.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa, yazdırılan karakter veya negatif bir değer döndürür. Varsa *biçimi* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için ayarlar ve işlev dönüşleri -1 yürütülmesine izin veriliyorsa **errno** için **EINVAL**. Varsa **EOF** (0xFFFF) içinde karşılaştı *bağımsız değişkeni*, işlevi -1 döndürür.

Hakkında bilgi için **errno** ve hata kodları bakın [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Printf** işlevi biçimlendirir ve bir dizi karakter ve standart çıktı akışı değerlere yazdırır **stdout**. Bağımsız değişkenler izlerseniz *biçimi* dize *biçimi* dize bağımsız değişkenleri için çıktı biçimi belirlemek belirtimleri içermesi gerekir. **Printf** ve [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md) durumlar dışında aynı şekilde davranır **printf** Yazar çıkışı **stdout** yerine bir hedefe türü **dosyası** .

**wprintf** bir joker karakter sürümü **printf**; *biçimi* bir joker karakter dizesidir. **wprintf** ve **printf** akış ANSI modunda açılırsa aynı şekilde davranır. **Printf** şu anda çıktı bir UNICODE akışa desteklemiyor.

Bu işlevleri sürümlerini **_l** soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|tanımlanan _UNICODE|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tprintf**|**Printf**|**Printf**|**wprintf**|

*Biçimi* bağımsız değişkeni sıradan karakterlerinden kaçış sıraları oluşur ve (bağımsız değişkenler izlerseniz *biçimi*) biçimlendirir. Kaçış dizileri ve sıradan karakterler kopyalanır **stdout** görünümlerini sırasıyla. Örneğin, satır:

```C
printf("Line one\n\t\tLine two\n");
```

bir çıktı üretir:

```Output
Line one
        Line two
```

[Biçimlendirir](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) her zaman yüzde işaretiyle başlar (**%**) ve soldan sağa okuyun. Zaman **printf** ilk biçim belirtimi (varsa), karşılaştığında sonra ilk bağımsız değişkenin değeri dönüştürür *biçimi* ve buna göre çıkarır. İkinci biçim belirtimi dönüştürülür ve çıkış, ikinci bağımsız değişkeni neden olur ve benzeri. Biçim belirtimleri sayısından daha fazla bağımsız değişken varsa, ek bağımsız değişkenleri göz ardı edilir. Tüm biçim belirtimleri için yeterli bağımsız değişken varsa sonuçları tanımlanmamış.

> [!IMPORTANT]
> Emin *biçimi* kullanıcı tanımlı bir dize değil.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tprintf**|**Printf**|**Printf**|**wprintf**|
|**_tprintf_l**|**_printf_l**|**_printf_l**|**_wprintf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Printf**, **_printf_l**|\<stdio.h >|
|**wprintf**, **_wprintf_l**|\<stdio.h > veya \<wchar.h >|

Konsol Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsol ile ilişkili standart akış tanıtıcıları **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri UWP uygulamalarında kullanabilmek için önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
[_set_output_format](../../c-runtime-library/set-output-format.md)<br/>
