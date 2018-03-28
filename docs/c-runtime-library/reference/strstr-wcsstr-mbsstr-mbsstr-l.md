---
title: strstr, wcsstr, _mbsstr, _mbsstr_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbsstr
- wcsstr
- _mbsstr_l
- strstr
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _fstrstr
- _ftcsstr
- strstr
- wcsstr
- _mbsstr
- _tcsstr
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], searching
- mbsstr function
- _ftcsstr function
- ftcsstr function
- fstrstr function
- _tcsstr function
- substrings, finding
- mbsstr_l function
- tcsstr function
- _mbsstr function
- wcsstr function
- _fstrstr function
- _mbsstr_l function
- strstr function
ms.assetid: 03d70c3f-2473-45cb-a5f8-b35beeb2748a
caps.latest.revision: ''
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d56fc0f254a426eea10abec979ff7d656659bd82
ms.sourcegitcommit: 604907f77eb6c5b1899194a9877726f3e8c2dabc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
---
# <a name="strstr-wcsstr-mbsstr-mbsstrl"></a>strstr, wcsstr, _mbsstr, _mbsstr_l
Bir işaretçi bir arama dizesi bir dizedeki ilk örneğini döndürür.  
  
> [!IMPORTANT]
>  `_mbsstr` ve `_mbsstr_l` Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *strstr(  
   const char *str,  
   const char *strSearch   
); // C only  
char *strstr(  
   char *str,  
   const char *strSearch   
); // C++ only  
const char *strstr(  
   const char *str,  
   const char *strSearch   
); // C++ only  
wchar_t *wcsstr(  
   const wchar_t *str,  
   const wchar_t *strSearch   
); // C only  
wchar_t *wcsstr(  
   wchar_t *str,  
   const wchar_t *strSearch   
); // C++ only  
const wchar_t *wcsstr(  
   const wchar_t *str,  
   const wchar_t *strSearch   
); // C++ only  
unsigned char *_mbsstr(  
   const unsigned char *str,  
   const unsigned char *strSearch   
); // C only  
unsigned char *_mbsstr(  
   unsigned char *str,  
   const unsigned char *strSearch   
); // C++ only  
const unsigned char *_mbsstr(  
   const unsigned char *str,  
   const unsigned char *strSearch   
); // C++ only  
unsigned char *_mbsstr_l(  
   const unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C only  
unsigned char *_mbsstr_l(  
   unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbsstr_l(  
   const unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 `str`  
 Aranacak dize null ile sonlandırılmış.  
  
 `strSearch`  
 Aranacak dizeyi null sonlandırıldı.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşaretçi ilk örneğini döndüren `strSearch` içinde `str`, veya `NULL` varsa `strSearch` görünmez `str`. Varsa `strSearch` işaret sıfır uzunlukta bir dizeye işlevi döndürür `str`.  
  
## <a name="remarks"></a>Açıklamalar  
 `strstr` İşlevi ilk örneğini bir işaretçi döndürür `strSearch` içinde `str`. Arama null karakterlerini sonlandırma içermez. `wcsstr` joker karakter sürümü `strstr` ve `_mbsstr` çok baytlı karakter sürümüdür. Bağımsız değişkenleri ve dönüş değerini `wcsstr` joker karakter olan dizeleri; bu `_mbsstr` çok baytlı karakter dizeleri belirtilmiştir. `_mbsstr` parametreleri doğrular. Varsa `str` veya `strSearch` olan `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa `_mbsstr` ayarlar `errno` için `EINVAL` ve 0 döndürür. `strstr` ve `wcsstr` parametrelerini doğrulamaz. Bu üç işlevler aynı şekilde aksi davranır.  
  
> [!IMPORTANT]
>  Bu işlevlerin bir tehdit bir arabellek taşması sorun etkileyebilir. Arabellek taşması sorunları unwarranted ayrıcalık yükselmesine neden olabilir rastgele kod yürütmeyi izin verebilir nedeni bir sistem saldırmak için kullanılabilir. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 C, bu işlevler ele bir `const` ilk bağımsız değişken için bir işaretçi. C++'da, iki aşırı kullanılabilir. Bir işaretçi alır aşırı `const` gösteren bir işaretçi döndürür `const`; bir işaretçi olmayan alır sürüm`const` gösteren bir işaretçi olmayan döndürür`const`. Makro `_CRT_CONST_CORRECT_OVERLOADS` her iki tanımlanan `const` ve olmayan-`const` bu işlevler sürümlerinde kullanılabilir. Olmayan gerektiriyorsa`const` hem C++ aşırı davranışını tanımlayın simgenin `_CONST_RETURN`.  
  
 Çıkış değerini yerel ayar kategorisi ayarı tarafından etkilenen `LC_CTYPE`; daha fazla bilgi için bkz: [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Bu işlevlerin olmayan sürümleri `_l` bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; olan sürümleri `_l` soneki, bunun yerine geçirilen yerel ayar parametresi kullandıkları dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|  
|**yok**|**yok**|`_mbsstr_l`|**yok**|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`strstr`|\<String.h >|  
|`wcsstr`|\<String.h > veya \<wchar.h >|  
|`_mbsstr`, `_mbsstr_l`|\<Mbstring.h >|  
  
 Uyumluluğu hakkında daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_strstr.c  
  
#include <string.h>  
#include <stdio.h>  
  
char str[] =    "lazy";  
char string[] = "The quick brown dog jumps over the lazy fox";  
char fmt1[] =   "         1         2         3         4         5";  
char fmt2[] =   "12345678901234567890123456789012345678901234567890";  
  
int main( void )  
{  
   char *pdest;  
   int  result;  
   printf( "String to be searched:\n   %s\n", string );  
   printf( "   %s\n   %s\n\n", fmt1, fmt2 );  
   pdest = strstr( string, str );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf( "%s found at position %d\n", str, result );  
   else  
      printf( "%s not found\n", str );  
}  
```  
  
```Output  
String to be searched:  
   The quick brown dog jumps over the lazy fox  
            1         2         3         4         5  
   12345678901234567890123456789012345678901234567890  
  
lazy found at position 36  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, _mbscspn, _mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](../../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [basic_string::Find](../../standard-library/basic-string-class.md#find)  
