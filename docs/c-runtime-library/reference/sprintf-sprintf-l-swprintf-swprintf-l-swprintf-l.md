---
title: sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __swprintf_l
- sprintf
- _sprintf_l
- _swprintf_l
- swprintf
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
- ntdll.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _stprintf_l
- __swprintf_l
- sprintf_l
- swprintf
- _sprintf_l
- sprintf
- _stprintf
- stprintf_l
dev_langs: C++
helpviewer_keywords:
- _swprintf_l function
- _stprintf function
- __swprintf_l function
- stprintf function
- sprintf function
- _sprintf_l function
- _stprintf_l function
- swprintf function
- strings [C++], writing to
- _CRT_NON_CONFORMING_SWPRINTFS
- swprintf_l function
- stprintf_l function
- sprintf_l function
- formatted text [C++]
ms.assetid: f6efe66f-3563-4c74-9455-5411ed939b81
caps.latest.revision: "36"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8e535097a5a46a952c19224f575a49107869dea3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="sprintf-sprintfl-swprintf-swprintfl-swprintfl"></a>sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l
Biçimlendirilmiş verileri dizeye yazma. Bu işlevlerin bazıları daha güvenli sürümleri kullanılabilir; bkz: [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md). Güvenli sürümlerini `swprintf` ve `_swprintf_l` yararlanabilir mi bir `count` parametresi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int sprintf(  
   char *buffer,  
   const char *format [,  
   argument] ...   
);  
int _sprintf_l(  
   char *buffer,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int swprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format [,  
   argument]...  
);  
int _swprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
int __swprintf_l(  
   wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
template <size_t size>  
int sprintf(  
   char (&buffer)[size],  
   const char *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _sprintf_l(  
   char (&buffer)[size],  
   const char *format,  
   locale_t locale [,  
   argument] ...   
); // C++ only  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `buffer`  
 Çıktı için depolama konumu  
  
 `count`  
 Bu işlev Unicode sürümünü depolamak için karakter sayısı.  
  
 `format`  
 Denetim Biçimlendir dize  
  
 `argument`  
 İsteğe bağlı bağımsız değişkenler  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
 Daha fazla bilgi için bkz: [biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yazılan karakter sayısını veya bir hata oluştuysa -1. Varsa `buffer` veya `format` null işaretçi açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve `errno` için `EINVAL`.  
  
 `sprintf`depolanan bayt sayısını verir `buffer`, sonlandırma null karakteri sayım değil. `swprintf`depolanan geniş karakter sayısını verir `buffer`, sonlandırma null geniş karakter sayım değil.  
  
## <a name="remarks"></a>Açıklamalar  
 `sprintf` İşlevi biçimlendirir ve bir dizi karakter ve değerleri depolar `buffer`. Her `argument` (varsa) dönüştürülür ve çıktı içinde karşılık gelen biçimi belirtimlerine göre `format`. Biçim sıradan karakterden oluşan ve aynı form ve olarak işlev `format` bağımsız değişkeni için [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md). Bir null karakter yazılmış son karakter sonra eklenir. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.  
  
> [!IMPORTANT]
>  Kullanarak `sprintf`, yazılan karakterleri kullanarak kod anlamına sayısını sınırlamak için bir yolu yoktur `sprintf` arabellek taşmaları açıktır. İlgili işlevi kullanmayı [_snprintf](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md), en fazla yazılması için karakter sayısını belirtir `buffer`, veya [_scprintf](../../c-runtime-library/reference/scprintf-scprintf-l-scwprintf-scwprintf-l.md) ne kadar büyük bir arabellek gerekli olduğunu belirlemek için. Ayrıca, emin `format` kullanıcı tanımlı bir dize değil.  
  
 `swprintf`bir joker karakter sürümü `sprintf`; işaretçi bağımsız değişkenleri `swprintf` joker karakter dizelerdir. Kodlama hataları algılama `swprintf` , farklı olabilir `sprintf`. `swprintf`ve `fwprintf` durumlar dışında aynı şekilde davranır `swprintf` bir dize yerine bir hedef türü çıktısı Yazar `FILE`, ve `swprintf` gerektirir `count` parametre olarak karakter sayısını belirtin yazılır. Bu işlevleri sürümlerini `_l` soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.  
  
 `swprintf`ISO C ikinci parametre gerektiren standart, uyumlu `count`, türü `size_t`. Eski standart olmayan davranış zorlamak için tanımlamak `_CRT_NON_CONFORMING_SWPRINTFS`. Kod yeni uyumluluğunu davranışı kullanmak için değiştirilmesi gereken şekilde sonraki bir sürümde eski davranışı, kaldırılmış olabilir.  
  
 C++'da, bu işlevlerin daha yeni, güvenli ortaklarınıza çağırma şablon aşırı yüklemeleri bu işlevler vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_stprintf`|`sprintf`|`sprintf`|`_swprintf`|  
|`_stprintf_l`|`_sprintf_l`|`_sprintf_l`|`__swprintf_l`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`sprintf`, `_sprintf_l`|\<stdio.h >|  
|`swprintf`, `_swprintf_l`|\<stdio.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_sprintf.c  
// compile with: /W3  
// This program uses sprintf to format various  
// data and place them in the string named buffer.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  buffer[200], s[] = "computer", c = 'l';  
   int   i = 35, j;  
   float fp = 1.7320534f;  
  
   // Format and print various data:   
   j  = sprintf( buffer,     "   String:    %s\n", s ); // C4996  
   j += sprintf( buffer + j, "   Character: %c\n", c ); // C4996  
   j += sprintf( buffer + j, "   Integer:   %d\n", i ); // C4996  
   j += sprintf( buffer + j, "   Real:      %f\n", fp );// C4996  
   // Note: sprintf is deprecated; consider using sprintf_s instead  
  
   printf( "Output:\n%s\ncharacter count = %d\n", buffer, j );  
}  
```  
  
```Output  
Output:  
   String:    computer  
   Character: l  
   Integer:   35  
   Real:      1.732053  
  
character count = 79  
```  
  
## <a name="example"></a>Örnek  
  
```  
// crt_swprintf.c  
// wide character example  
// also demonstrates swprintf returning error code  
#include <stdio.h>  
  
int main( void )  
{  
   wchar_t buf[100];  
   int len = swprintf( buf, 100, L"%s", L"Hello world" );  
   printf( "wrote %d characters\n", len );  
   len = swprintf( buf, 100, L"%s", L"Hello\xffff world" );  
   // swprintf fails because string contains WEOF (\xffff)  
   printf( "wrote %d characters\n", len );  
}  
```  
  
```Output  
wrote 11 characters  
wrote -1 characters  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [Printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, _sscanf_l, swscanf, _swscanf_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vprintf işlevleri](../../c-runtime-library/vprintf-functions.md)