---
title: printf_s, _printf_s_l, wprintf_s, _wprintf_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
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
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1d891b5b049e83a621514da6981a8f836d687b7a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="printfs-printfsl-wprintfs-wprintfsl"></a>printf_s, _printf_s_l, wprintf_s, _wprintf_s_l
Biçimlendirilmiş çıkışı için standart çıktı akışı yazdırır. Bu sürümleri [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
  
#### <a name="parameters"></a>Parametreler  
 `format`  
 Denetim biçimlendirin.  
  
 `argument`  
 İsteğe bağlı bağımsız değişkenler.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir hata oluşursa, yazdırılan karakter veya negatif bir değer döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `printf_s` İşlevi biçimlendirir ve bir dizi karakter ve standart çıktı akışı değerlere yazdırır `stdout`. Bağımsız değişkenler izlerseniz *biçimi* dize `format` dize bağımsız değişkenleri için çıktı biçimi belirlemek belirtimleri içermesi gerekir.  
  
 Arasındaki temel fark `printf_s` ve `printf` olan `printf_s` ancak geçerli biçimlendirme karakterlerini biçim dizesi denetler `printf` yalnızca biçim dizesi null işaretçi olup olmadığını denetler. Ya da denetimi başarısız olur, bir geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için ayarlar ve işlev dönüşleri -1 yürütülmesine izin veriliyorsa `errno` için `EINVAL`.  
  
 Hakkında bilgi için `errno` ve hata kodları bakın [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `printf_s`ve `fprintf_s` durumlar dışında aynı şekilde davranır `printf_s` Yazar çıkışı `stdout` yerine bir hedefe türü `FILE`. Daha fazla bilgi için bkz: [fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md).  
  
 `wprintf_s`bir joker karakter sürümü `printf_s`; `format` bir joker karakter dizesidir. `wprintf_s`ve `printf_s` akış ANSI modunda açılırsa aynı şekilde davranır. `printf_s`şu anda çıktı bir UNICODE akışa desteklemiyor.  
  
 Bu işlevleri sürümlerini `_l` soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|tanımlanan _UNICODE|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tprintf_s`|`printf_s`|`printf_s`|`wprintf_s`|  
|`_tprintf_s_l`|`_printf_s_l`|`_printf_s_l`|`_wprintf_s_l`|  
  
 `format` Bağımsız değişkeni sıradan karakterlerinden kaçış sıraları oluşur ve (bağımsız değişkenler izlerseniz `format`) biçimlendirir. Kaçış dizileri ve sıradan karakterler kopyalanır `stdout` görünümlerini sırasıyla. Örneğin, satır  
  
```  
printf_s("Line one\n\t\tLine two\n");   
```  
  
 bir çıktı üretir  
  
```  
Line one  
        Line two  
```  
  
 [Biçimlendirir](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) her zaman yüzde işaretiyle başlar (`%`) ve soldan sağa okuyun. Zaman `printf_s` ilk biçim belirtimi (varsa), karşılaştığında sonra ilk bağımsız değişkenin değeri dönüştürür `format` ve buna göre çıkarır. İkinci biçim belirtimi dönüştürülür ve çıkış, ikinci bağımsız değişkeni neden olur ve benzeri. Biçim belirtimleri sayısından daha fazla bağımsız değişken varsa, ek bağımsız değişkenleri göz ardı edilir. Tüm biçim belirtimleri için yeterli bağımsız değişken varsa sonuçları tanımlanmamış.  
  
> [!IMPORTANT]
>  Emin `format` kullanıcı tanımlı bir dize değil.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`printf_s`, `_printf_s_l`|\<stdio.h >|  
|`wprintf_s`, `_wprintf_s_l`|\<stdio.h > veya \<wchar.h >|  
  
 Konsol desteklenmeyen [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar. Konsol ile ilişkili standart akış tanıtıcıları —`stdin`, `stdout`, ve `stderr`— C çalışma zamanı işlevleri de kullanabilmek için önce yeniden yönlendirilmesi gerekiyor [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar. Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="sample-output"></a>Örnek Çıktı  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vprintf işlevleri](../../c-runtime-library/vprintf-functions.md)