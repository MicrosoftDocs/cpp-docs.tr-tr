---
title: _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _stricmp_l
- _mbsicmp
- _wcsicmp
- _mbsicmp_l
- _stricmp
- _wcsicmp_l
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ftcsicmp
- _stricmp
- wcsicmp_l
- _wcsicmp
- _tcsicmp
- _strcmpi
- stricmp_l
- _mbsicmp
- _fstricmp
- mbsicmp_l
- mbsicmp
dev_langs: C++
helpviewer_keywords:
- _wcsicmp function
- _stricmp_l function
- fstricmp function
- _tcsicmp function
- ftcsicmp function
- string comparison [C++], lowercase
- _wcsicmp_l function
- _fstricmp function
- strings [C++], comparing
- mbsicmp function
- _ftcsicmp function
- _mbsicmp_l function
- wcsicmp_l function
- _stricmp function
- _mbsicmp function
- tcsicmp function
- stricmp_l function
- mbsicmp_l function
- _strcmpi function
ms.assetid: 0e1ee515-0d75-435a-a445-8875d4669b50
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15b581d0d47da824f1faaade1214d1320e29bb03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="stricmp-wcsicmp-mbsicmp-stricmpl-wcsicmpl-mbsicmpl"></a>_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l
Dizeleri büyük küçük harf duyarsız bir karşılaştırma gerçekleştirir.  
  
> [!IMPORTANT]
>  `_mbsicmp`ve `_mbsicmp_l` Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _stricmp(  
   const char *string1,  
   const char *string2   
);  
int _wcsicmp(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbsicmp(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _stricmp_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale  
);  
int _wcsicmp_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale  
);  
int _mbsicmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `string1, string2`  
 Karşılaştırılacak null ile sonlandırılmış dizeler.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri ilişkisi gösterir `string1` için `string2` gibi.  
  
|Dönüş değeri|Açıklama|  
|------------------|-----------------|  
|< 0|`string1`küçüktür`string2`|  
|0|`string1`aynı`string2`|  
|> 0|`string1`büyüktür`string2`|  
  
 Bir hata `_mbsicmp` döndürür `_NLSCMPERROR`, içinde tanımlanan \<string.h > ve \<mbstring.h >.  
  
## <a name="remarks"></a>Açıklamalar  
 `_stricmp` İşlev ordinally karşılaştırır `string1` ve `string2` ilişkilerini gösteren bir değer küçük ve döndürür her karakter dönüştürme sonra. `_stricmp`farklı `_stricoll` bakımından `_stricmp` karşılaştırma tarafından etkilenen yalnızca `LC_CTYPE`, hangi karakterden büyük ve küçük belirler. `_stricoll` İşlevi karşılaştırır dizeleri hem göre `LC_CTYPE` ve `LC_COLLATE` durum ve harmanlama sırasını içeren yerel ayar kategorileri. Hakkında daha fazla bilgi için `LC_COLLATE` kategorisi, bkz: [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) ve [yerel ayar kategorileri](../../c-runtime-library/locale-categories.md). Bu işlevlerin sürümleri `_l` soneki geçerli yerel ayar için yerel ayara bağımlı davranışı kullanın. Bunun yerine geçirilen yerel ayar kullanmasını dışında soneki sürümleriyle aynıdır. Yerel ayar ayarlı değil, C yerel ayar kullanılır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
> [!NOTE]
>  `_stricmp`eşdeğer olan `_strcmpi`. Birbirinin yerine kullanılabilir ancak `_stricmp` tercih edilen standardıdır.  
  
 `_strcmpi` İşlevi eşdeğerdir `_stricmp` ve yalnızca geriye dönük uyumluluk için sağlanır.  
  
 Çünkü `_stricmp` karşılaştırmaları, küçük harf beklenmeyen davranışlara neden olabilir.  
  
 Ne zaman göstermeye durumda dönüştürme `_stricmp` sonucu etkiler karşılaştırması, iki dizeyi JOHNSTON ve JOHN_HENRY olduğunu varsayın. JOHNSTON değerinden JOHN_HENRY olarak kabul edilmelidir dizesi "_" küçük S. daha düşük bir ASCII değer içerdiğinden Aslında, ASCII değeri 91 96 arasındaki sahip herhangi bir karakter değerinden herhangi bir harf kabul edilir.  
  
 Varsa [strcmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md) işlevi yerine kullanılır `_stricmp`, JOHN_HENRY JOHNSTON büyük olacaktır.  
  
 `_wcsicmp`ve `_mbsicmp` joker karakter ve çok baytlı karakter sürümleri `_stricmp`. Bağımsız değişkenleri ve dönüş değerini `_wcsicmp` joker karakter olan dizeleri; bu `_mbsicmp` çok baytlı karakter dizeleri belirtilmiştir. `_mbsicmp`çok baytlı karakter sıralarının geçerli birden çok baytlı kod sayfasına göre tanır ve döndürür `_NLSCMPERROR` bir hata. Daha fazla bilgi için bkz: [kod sayfaları](../../c-runtime-library/code-pages.md). Bu üç işlevler aynı şekilde aksi davranır.  
  
 `_wcsicmp`ve `wcscmp` durumlar dışında aynı şekilde davranır `wcscmp` değişkenlerinin karşılaştırma önce küçük harf dönüştürmez. `_mbsicmp`ve `_mbscmp` durumlar dışında aynı şekilde davranır `_mbscmp` değişkenlerinin karşılaştırma önce küçük harf dönüştürmez.  
  
 Çağırmanız gerekir [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) için `_wcsicmp` Latin 1 karakter ile çalışmak için. C yerel ayar yürürlükte varsayılan olarak, bu nedenle, örneğin, ä Ä eşit karşılaştırmak değil'dır. Çağrı `setlocale` çağırmadan önce C yerel dışında herhangi bir yerel ayarı ile `_wcsicmp`. Aşağıdaki örnek gösterilmektedir nasıl `_wcsicmp` yerel duyarlıdır:  
  
```  
// crt_stricmp_locale.c  
#include <string.h>  
#include <stdio.h>  
#include <locale.h>  
  
int main() {  
   setlocale(LC_ALL,"C");   // in effect by default  
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare fails  
   setlocale(LC_ALL,"");  
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare succeeds  
}  
```  
  
 Alternatif çağırmaktır [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md) ve döndürülen yerel ayar nesnesini parametre olarak geçirmek `_wcsicmp_l`.  
  
 Tüm bu işlevlerin kendi parametreleri doğrulayın. Her iki `string1` veya `string2` null işaretçiler açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş `_NLSCMPERROR` ve `errno` için `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsicmp`|`_stricmp`|`_mbsicmp`|`_wcsicmp`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_stricmp`, `_stricmp_l`|\<String.h >|  
|`_wcsicmp`, `_wcsicmp_l`|\<String.h > veya \<wchar.h >|  
|`_mbsicmp`, `_mbsicmp_l`|\<Mbstring.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_stricmp.c  
  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown dog jumps over the lazy fox";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
  
   // Case sensitive  
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );  
   result = strcmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof(tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof(tmp), "equal to" );  
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );  
  
   // Case insensitive (could use equivalent _stricmp)  
   result = _stricmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof(tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof(tmp), "equal to" );  
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );  
}  
```  
  
```Output  
Compare strings:  
   The quick brown dog jumps over the lazy fox  
   The QUICK brown dog jumps over the lazy fox  
  
   strcmp:   String 1 is greater than string 2  
   _stricmp:  String 1 is equal to string 2  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [_memicmp, _memicmp_l](../../c-runtime-library/reference/memicmp-memicmp-l.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcoll işlevleri](../../c-runtime-library/strcoll-functions.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)