---
title: _lfind_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _lfind_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- lfind_s
- _lfind_s
dev_langs: C++
helpviewer_keywords:
- linear searching
- keys, finding in arrays
- lfind_s function
- arrays [CRT], searching
- searching, linear
- _lfind_s function
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a49c732be3c1f378340d00c414acee91e6e62978
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="lfinds"></a>_lfind_s
Belirtilen anahtar için doğrusal arama gerçekleştirir. Bir sürümünü [_lfind](../../c-runtime-library/reference/lfind.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *_lfind_s(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `key`  
 Aranacak nesne.  
  
 `base`  
 Arama veri tabanı işaretçi.  
  
 `num`  
 Dizi öğe sayısı.  
  
 `size`  
 Dizi öğeleri bayt cinsinden boyutu.  
  
 `compare`  
 İşaretçi karşılaştırması yordama. İlk parametre `context` işaretçi. İkinci parametre için arama anahtar bir işaretçidir. Üçüncü parametre anahtarı ile Karşılaştırılacak dizi öğesi bir işaretçidir.  
  
 `context`  
 Karşılaştırma işlevinde erişilebilen bir nesne için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Anahtar bulunursa, `_lfind_s` dizisi öğesine bir işaretçi döndüren `base` eşleşen `key`. Anahtar bulunamazsa `_lfind_s` döndürür `NULL`.  
  
 İşlev için geçersiz parametreler aktarılırsa geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevi döndürür `NULL`.  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|anahtar|taban|compare|NUM|size|errno|  
|---------|----------|-------------|---------|----------|-----------|  
|`NULL`|tüm|tüm|tüm|tüm|`EINVAL`|  
|tüm|`NULL`|tüm|!= 0|tüm|`EINVAL`|  
|tüm|tüm|tüm|tüm|sıfır|`EINVAL`|  
|tüm|tüm|`NULL`|bir|tüm|`EINVAL`|  
  
## <a name="remarks"></a>Açıklamalar  
 `_lfind_s` İşlevi gerçekleştiren değeri için doğrusal arama `key` dizisindeki `num` öğeleri, her biri `width` bayt sayısı. Farklı `bsearch_s`, `_lfind_s` sıralanacak dizi gerektirmez. `base` Bağımsız değişkeni bir işaretçidir aranacağı dizinin tabanı. `compare` Bağımsız değişkeni bir işaretçidir iki dizi öğeleri karşılaştırır ve ilişkilerini belirten bir değer döndüren bir kullanıcı tarafından sağlanan yordam. `_lfind_s`çağrıları `compare` geçirme, arama sırasında rutin bir veya birden çok kez `context` işaretçi ve her çağrıda iki dizi öğeleri işaretçiler. `compare` Yordamı öğeleri karşılaştırın ardından (öğeleri farklı sıfır olmayan anlamına gelir) dönün veya 0 (öğeleri aynı olduğu anlamına gelir).  
  
 `_lfind_s`benzer `_lfind` eklenmesi dışında `context` işaretçi karşılaştırması işlevinin bağımsız değişkenleri ve işlev parametre listesi. `context` İşaretçi Aranan veri yapısı bir nesnenin parçası ise yararlı olabilir ve `compare` işlevi nesnenin üyelerine erişme gerekiyor. `compare` İşlevi uygun nesne türüne ve erişim üyeleri bu nesnenin void işaretçi çevirebilirsiniz. Eklenmesi `context` parametreyi yapar `_lfind_s` daha güvenli ek bağlam verileri kullanılabilir hale getirmek için statik değişkenler kullanımıyla ilişkili yeniden giriş hataları önlemek için kullanılabileceğinden `compare` işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_lfind_s`|\<Search.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_lfind_s.cpp  
// This program uses _lfind_s to search a string array,  
// passing a locale as the context.  
// compile with: /EHsc  
#include <stdlib.h>  
#include <stdio.h>  
#include <search.h>  
#include <process.h>  
#include <locale.h>  
#include <locale>  
#include <windows.h>  
using namespace std;  
  
// The sort order is dependent on the code page.  Use 'chcp' at the  
// command line to change the codepage.  When executing this application,  
// the command prompt codepage must match the codepage used here:  
  
#define CODEPAGE_850  
  
#ifdef CODEPAGE_850  
// Codepage 850 is the OEM codepage used by the command line,  
// so \x00e1 is the German Sharp S  
  
char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
  
#define GERMAN_LOCALE "German_Germany.850"  
  
#endif  
  
#ifdef CODEPAGE_1252  
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df  
   // for the German Sharp S  
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
  
#define GERMAN_LOCALE "German_Germany.1252"  
  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making it vulnerable to thread conflicts  
// (if this were a multithreaded program).  
  
int compare( void *pvlocale, const void *str1, const void *str2)  
{  
    char *s1 = *(char**)str1;  
    char *s2 = *(char**)str2;  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(  
       s1, s1+strlen(s1),  
       s2, s2+strlen(s2) );  
}  
  
void find_it( char *key, char *array[], unsigned int num, locale &loc )  
{  
   char **result = (char **)_lfind_s( &key, array,   
                      &num, sizeof(char *), compare, &loc );  
   if( result )  
      printf( "%s found\n", *result );  
   else  
      printf( "%s not found\n", key );  
}  
  
int main( )  
{  
   find_it( "weit", array1, sizeof(array1)/sizeof(char*), locale(GERMAN_LOCALE) );  
}  
```  
  
```Output  
weit found  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arama ve sıralama](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort_s](../../c-runtime-library/reference/qsort-s.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)