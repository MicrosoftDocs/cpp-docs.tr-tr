---
title: scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wscanf_s
- _wscanf_s_l
- scanf_s
- _scanf_s_l
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
- wscanf_s
- _tscanf_s_l
- _wscanf_s_l
- scanf_s
- _tscanf_s
- _scanf_s_l
dev_langs: C++
helpviewer_keywords:
- reading data [C++], from input streams
- buffers [C++], buffer overruns
- _scanf_s_l function
- _wscanf_s_l function
- tscanf_s_l function
- tscanf_s function
- scanf_s function
- data [C++], reading from input stream
- wscanf_s function
- _tscanf_s_l function
- _tscanf_s function
- scanf_s_l function
- formatted data [C++], from input streams
- wscanf_s_l function
- buffers [C++], avoiding overruns
ms.assetid: 42cafcf7-52d6-404a-80e4-b056a7faf2e5
caps.latest.revision: "33"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7bbd71d42e728a39e0c8c20f9a496832f45d33ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="scanfs-scanfsl-wscanfs-wscanfsl"></a>scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l
Standart giriş akışı verileri okuma biçimlendirilmiş. Bu sürümleri [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int scanf_s(  
   const char *format [,  
   argument]...   
);  
int _scanf_s_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wscanf_s(  
   const wchar_t *format [,  
   argument]...   
);  
int _wscanf_s_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `format`  
 Biçim denetim dizesi.  
  
 `argument`  
 İsteğe bağlı bağımsız değişkenler.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı bir şekilde dönüştürülür ve atanan alan sayısını döndürür; dönüş değerini okumak ancak atanmamış alanları içermez. Dönüş değeri 0, hiçbir alan atandığını belirtir. Dönüş değeri `EOF` bir hata için veya dosya sonu karakteri veya dize son karakter bir karakter okumak için ilk deneme karşılaştıysanız. Varsa `format` olan bir `NULL` işaretçi, geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `scanf_s` ve `wscanf_s` dönmek `EOF` ve `errno` için `EINVAL`.  
  
 Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `scanf_s` işlevi, `stdin` standart giriş akışından verileri okur ve verileri, `argument` bağımsız değişken listesi tarafından verilen konumlara yazar. Her bir `argument`, bir `format`'da tür tanımlayıcıyla karşılık gelen bir değişken türüne bir işaretçi olmalıdır. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.  
  
 `wscanf_s`bir joker karakter sürümü `scanf_s`; `format` bağımsız değişkeni `wscanf_s` bir joker karakter dizesidir. `wscanf_s`ve `scanf_s` akış ANSI modunda açılırsa aynı şekilde davranır. `scanf_s`UNICODE akışı girişten şu anda desteklemiyor.  
  
 `_l` sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine iletilen yerel ayar parametresini kullanmaları hariç aynıdır.  
  
 Farklı `scanf` ve `wscanf`, `scanf_s` ve `wscanf_s` tüm giriş parametreleri türü için belirtilen arabellek boyutu gerektiren `c`, `C`, `s`, `S`, veya dize olan denetim kümeleri içine `[]`. Arabellek boyutu karakter cinsinden işaretçinin arabellek veya değişken hemen ardından ek bir parametre olarak geçirilir. Örneğin, bir dize okuyorsanız, bu dize için arabellek boyutu şöyle aktarılır:  
  
 `char s[10];`  
  
 `scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9`  
  
 Arabellek boyutu sonlandırma null içerir. Okunan belirtecin arabelleğe sığmasını sağlamak için bir genişlik belirtimi alanını kullanabilirsiniz. Genişlik belirtimi alan kullanılır ve okunan belirteci arabellek sığmayacak kadar büyük ise, hiçbir şey bu arabelleğe yazılır.  
  
> [!NOTE]
>  Boyutu parametresi türünde `unsigned`değil `size_t`. Dönüştürmek için bir statik atama kullanın bir `size_t` değeri `unsigned` 64 bit için derleme yapılandırmaları.  
  
 Aşağıdaki örnekte, arabellek boyutu parametresinin bayt sayısını değil en fazla karakter sayısını açıkladığı gösterilir. `wscanf_s` çağrısında, arabellek türü tarafından belirtilen karakter genişliği, biçim tanımlayıcısı tarafından belirtilen karakter genişliği ile eşleşmiyor.  
  
```  
wchar_t ws[10];  
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));  
```  
  
 `S` biçim tanımlayıcısı, işlev tarafından desteklenen varsayılan genişliğin "karşıtı" olan karakter genişliğinin kullanımını gösterir. Karakter genişliği tek baytlıdır ancak işlev çift baytlı karakterleri destekler. Bu örnek, 9 adede kadar tek bayt geniş karakter dizesini okur ve bunları bir çift bayt genişliğinde karakter arabelleğine koyar. Karakterler tek baytlık değer olarak kabul edilir; ilk iki karakter `ws[0]` içinde depolanır, ikinci iki karakter `ws[1]` içinde depolanır ve bu şekilde devam eder.  
  
 Karakterler söz konusu olduğunda, tek bir karakter aşağıdaki gibi okunabilir:  
  
 `char c;`  
  
 `scanf_s("%c", &c, 1);`  
  
 Değersiz olmayan sonlandırılmış dizeler için birden çok karakter okunduğunda, tamsayılar genişlik belirtimi ve arabellek boyutu olarak kullanılır.  
  
 `char c[4];`  
  
 `scanf_s("%4c", &c, (unsigned)_countof(c)); // not null terminated`  
  
 Daha fazla bilgi için bkz: [sacnf genişlik belirtimi](../../c-runtime-library/scanf-width-specification.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tscanf_s`|`scanf_s`|`scanf_s`|`wscanf_s`|  
|`_tscanf_s_l`|`_scanf_s_l`|`_scanf_s_l`|`_wscanf_s_l`|  
  
 Daha fazla bilgi için bkz: [biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`scanf_s`, `_scanf_s_l`|\<stdio.h >|  
|`wscanf_s`, `_wscanf_s_l`|\<stdio.h > veya \<wchar.h >|  
  
 Konsol desteklenmeyen [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar. Konsol ile ilişkili standart akış tanıtıcıları —`stdin`, `stdout`, ve `stderr`— C çalışma zamanı işlevleri de kullanabilmek için önce yeniden yönlendirilmesi gerekiyor [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar. Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_scanf_s.c  
// This program uses the scanf_s and wscanf_s functions  
// to read formatted input.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int      i,  
            result;  
   float    fp;  
   char     c,  
            s[80];  
   wchar_t  wc,  
            ws[80];  
  
   result = scanf_s( "%d %f %c %C %s %S", &i, &fp, &c, 1,  
                     &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );  
   printf( "The number of fields input is %d\n", result );  
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c,  
           wc, s, ws);  
   result = wscanf_s( L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,  
                      &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );  
   wprintf( L"The number of fields input is %d\n", result );  
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp,  
            c, wc, s, ws);  
}  
```  
  
 Bu program, bu girdi verildiğinde aşağıdaki çıktıyı oluşturur:  
  
 `71 98.6 h z Byte characters`  
  
 `36 92.3 y n Wide characters`  
  
```Output  
The number of fields input is 6  
The contents are: 71 98.599998 h z Byte characters  
The number of fields input is 6  
The contents are: 36 92.300003 y n Wide characters  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [fscanf, _fscanf_l, fwscanf, _fwscanf_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [Printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [sscanf, _sscanf_l, swscanf, _swscanf_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)