---
title: sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _swprintf_s_l
- _sprintf_s_l
- swprintf_s
- sprintf_s
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
- swprintf_s
- sprintf_s
- stdio/sprintf_s
- stdio/swprintf_s
- stdio/_sprintf_s_l
- stdio/_swprintf_s_l
- _sprintf_s_l
- _swprintf_s_l
dev_langs:
- C++
helpviewer_keywords:
- stprintf_s function
- stprintf_s_l function
- swprintf_s_l function
- sprintf_s function
- swprintf_s function
- _swprintf_s_l function
- sprintf_s_l function
- _stprintf_s_l function
- _stprintf_s function
- _sprintf_s_l function
- formatted text [C++]
ms.assetid: 424f0a29-22ef-40e8-b565-969f5f57782f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0ebdfb3745378088799883e1263686c44a8239f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="sprintfs-sprintfsl-swprintfs-swprintfsl"></a>sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l
Biçimlendirilmiş verileri dizeye yazma. Sürümleri bunlar [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int sprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   ...   
);  
int _sprintf_s_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   locale_t locale,  
   ...   
);  
int swprintf_s(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   ...  
);  
int _swprintf_s_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   locale_t locale,  
   ...  
);  
template <size_t size>  
int sprintf_s(  
   char (&buffer)[size],  
   const char *format,  
   ...   
); // C++ only  
template <size_t size>  
int swprintf_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *format,  
   ...  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 `buffer`  
 Çıktı için depolama konumu  
  
 `sizeOfBuffer`  
 Depolanacak maksimum karakter sayısı.  
  
 `format`  
 Denetim Biçimlendir dize  
  
 `...`  
 Biçimlendirilecek isteğe bağlı bağımsız değişkenler  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
 Daha fazla bilgi için bkz: [biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yazılan karakter sayısını veya bir hata oluştuysa -1. Varsa `buffer` veya `format` null işaretçi `sprintf_s` ve `swprintf_s` -1 döndürür ve ayarlayın `errno` için `EINVAL`.  
  
 `sprintf_s` depolanan bayt sayısını verir `buffer`, sonlandırma null karakteri sayım değil. `swprintf_s` depolanan geniş karakter sayısını verir `buffer`, sonlandırma null geniş karakter sayım değil.  
  
## <a name="remarks"></a>Açıklamalar  
 `sprintf_s` İşlevi biçimlendirir ve bir dizi karakter ve değerleri depolar `buffer`. Her `argument` (varsa) dönüştürülür ve çıktı içinde karşılık gelen biçimi belirtimlerine göre `format`. Biçim sıradan karakterden oluşan ve aynı form ve olarak işlev `format` bağımsız değişkeni için [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md). Bir null karakter yazılmış son karakter sonra eklenir. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.  
  
 Arasındaki tek temel fark `sprintf_s` ve `sprintf` olan `sprintf_s` ancak geçerli biçimlendirme karakterlerini biçim dizesi denetler `sprintf` yalnızca biçimi dize veya arabellek olup olmadığını denetler `NULL` işaretçileri. Ya da denetimi başarısız olur, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için ayarlar ve işlev dönüşleri -1 yürütülmesine izin veriliyorsa `errno` için `EINVAL`.  
  
 Diğer temel fark `sprintf_s` ve `sprintf` olan `sprintf_s` karakter çıkış arabelleğinin boyutunu belirtme uzunluk parametresi alır. Arabellek sonlandırma null dahil olmak üzere biçimlendirilmiş metin için çok küçük ardından arabellek boş bir dize olarak bir null karakter koyarak ayarlanır `buffer[0]`, ve geçersiz parametre işleyicisi çağrılır. Farklı `_snprintf`, `sprintf_s` arabellek arabellek boyutu sıfır değilse sonlandırılmış emin garanti eder.  
  
 `swprintf_s` bir joker karakter sürümü `sprintf_s`; işaretçi bağımsız değişkenleri `swprintf_s` joker karakter dizelerdir. Kodlama hataları algılama `swprintf_s` , farklı olabilir `sprintf_s`. Bu işlevleri sürümlerini `_l` soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.  
  
 C++'da, Bu işlevlerden birinin kullanımını şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak bir boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan kaldırarak çıkarımını ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
 Sürümü vardır `sprintf_s` arabellek çok küçük ise olanlar ek denetim sunar. Daha fazla bilgi için bkz: [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](../../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_stprintf_s`|`sprintf_s`|`sprintf_s`|`swprintf_s`|  
|`_stprintf_s_l`|`_sprintf_s_l`|`_sprintf_s_l`|`_swprintf_s_l`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`sprintf_s`, `_sprintf_s_l`|C: \<stdio.h ><br /><br /> C++: \<cstdio > veya \<stdio.h >|  
|`swprintf_s`, `_swprintf_s_l`|C: \<stdio.h > veya \<wchar.h ><br /><br /> C++: \<cstdio >, \<cwchar >, \<stdio.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_sprintf_s.c  
// This program uses sprintf_s to format various  
// data and place them in the string named buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  buffer[200], s[] = "computer", c = 'l';  
   int   i = 35, j;  
   float fp = 1.7320534f;  
  
   // Format and print various data:   
   j  = sprintf_s( buffer, 200,     "   String:    %s\n", s );  
   j += sprintf_s( buffer + j, 200 - j, "   Character: %c\n", c );  
   j += sprintf_s( buffer + j, 200 - j, "   Integer:   %d\n", i );  
   j += sprintf_s( buffer + j, 200 - j, "   Real:      %f\n", fp );  
  
   printf_s( "Output:\n%s\ncharacter count = %d\n", buffer, j );  
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
// crt_swprintf_s.c  
// wide character example  
// also demonstrates swprintf_s returning error code  
#include <stdio.h>  
  
int main( void )  
{  
   wchar_t buf[100];  
   int len = swprintf_s( buf, 100, L"%s", L"Hello world" );  
   printf( "wrote %d characters\n", len );  
   len = swprintf_s( buf, 100, L"%s", L"Hello\xffff world" );  
   // swprintf_s fails because string contains WEOF (\xffff)  
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
 [vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)