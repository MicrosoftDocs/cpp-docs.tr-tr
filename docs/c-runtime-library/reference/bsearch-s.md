---
title: bsearch_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: bsearch_s
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
f1_keywords: bsearch_s
dev_langs: C++
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch_s function
ms.assetid: d5690d5e-6be3-4f1d-aa0b-5ca6dbded276
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a31ba82059748d49087546e2812d1f1fd32f4628
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bsearchs"></a>bsearch_s
İkili arama sıralanmış bir dizinin gerçekleştirir. Bu sürümüdür [bsearch](../../c-runtime-library/reference/bsearch.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *bsearch_s(   
   const void *key,  
   const void *base,  
   size_t num,  
   size_t width,  
   int ( __cdecl *compare ) ( void *, const void *key, const void *datum),  
   void * context  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `key`  
 Aranacak nesne.  
  
 `base`  
 Arama verilerini temel işaretçi.  
  
 `num`  
 Öğe sayısı.  
  
 `width`  
 Öğe genişliği.  
  
 `compare`  
 İki öğe karşılaştırır geri çağırma işlevi. İlk bağımsız değişken `context` işaretçi. İkinci bağımsız değişkeni gösteren bir işaretçidir `key` arama için. Üçüncü bağımsız değişkeni bir dizi öğesi ile Karşılaştırılacak işaretçidir `key`.  
  
 `context`  
 Karşılaştırma işlevinde erişilebilen bir nesne için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `bsearch_s`İşaretçi için bir örneğini döndüren `key` gösterdiği dizideki `base`. Varsa `key` , işlevi döndürür bulunamadı `NULL`. Dizi artan sıralama değil veya yinelenen kayıtları aynı anahtarlarla içeriyorsa, öngörülemeyen bir sonucudur.  
  
 İşlev için geçersiz parametreler aktarılırsa geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevi döndürür `NULL`. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|||||||  
|-|-|-|-|-|-|  
|`key`|`base`|`compare`|`num`|`width`|`errno`|  
|`NULL`|tüm|tüm|tüm|tüm|`EINVAL`|  
|tüm|`NULL`|tüm|!= 0|tüm|`EINVAL`|  
|tüm|tüm|tüm|tüm|= 0|`EINVAL`|  
|tüm|tüm|`NULL`|bir|tüm|`EINVAL`|  
  
## <a name="remarks"></a>Açıklamalar  
 `bsearch_s` İşlevi gerçekleştiren bir ikili arama sıralanmış bir dizi `num` öğeleri, her biri `width` bayt cinsinden boyutu. `base` Aranacak, dizi tabanı için bir işaretçi bir değerdir ve `key` Aranan değerdir. `compare` Parametresi, bir dizi öğesine istenen anahtarına karşılaştırır ve ilişkilerini belirterek aşağıdaki değerlerden birini döndürür ve kullanıcı tarafından sağlanan bir yordama bir işaretçidir:  
  
|Tarafından döndürülen değer `compare` yordamı|Açıklama|  
|-----------------------------------------|-----------------|  
|\< 0|Dizi öğesi değerinden anahtardır.|  
|0|Anahtar dizi öğesine eşittir.|  
|> 0|Dizi öğesi büyük anahtardır.|  
  
 `context` Aranan veri yapısı bir nesne bir parçasıdır ve karşılaştırma işlevi nesnenin üyelerine erişmesi durumunda işaretçi yararlı olabilir. `compare` İşlevi uygun nesne türüne ve erişim üyeleri bu nesnenin void işaretçi cast. Eklenmesi `context` parametreyi yapar `bsearch_s` ek bağlam verileri kullanılabilir hale getirmek için statik değişkenler kullanımıyla ilişkili yeniden giriş hataları önlemek için kullanılabilir olduğundan daha güvenli `compare` işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`bsearch_s`|\<stdlib.h > ve \<search.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Bu program bir dize dizisi ile sıralar [qsort_s](../../c-runtime-library/reference/qsort-s.md)ve "kat" word bulmak için bsearch_s kullanır.  
  
```  
// crt_bsearch_s.cpp  
// This program uses bsearch_s to search a string array,  
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
#define ENGLISH_LOCALE "English_US.850"  
#endif  
  
#ifdef CODEPAGE_1252  
#define ENGLISH_LOCALE "English_US.1252"  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making it vulnerable to thread conflicts  
// (if this were a multithreaded program).  
  
int compare( void *pvlocale, char **str1, char **str2)  
{  
    char *s1 = *str1;  
    char *s2 = *str2;  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(  
       s1, s1+strlen(s1),  
       s2, s2+strlen(s2) );  
}  
  
int main( void )  
{  
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};  
  
   char *key = "cat";  
   char **result;  
   int i;  
  
   /* Sort using Quicksort algorithm: */  
   qsort_s( arr,  
            sizeof(arr)/sizeof(arr[0]),  
            sizeof( char * ),  
            (int (*)(void*, const void*, const void*))compare,  
            &locale(ENGLISH_LOCALE) );  
  
   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */  
      printf( "%s ", arr[i] );  
  
   /* Find the word "cat" using a binary search algorithm: */  
   result = (char **)bsearch_s( &key,  
                                arr,  
                                sizeof(arr)/sizeof(arr[0]),  
                                sizeof( char * ),  
                                (int (*)(void*, const void*, const void*))compare,  
                                &locale(ENGLISH_LOCALE) );  
   if( result )  
      printf( "\n%s found at %Fp\n", *result, result );  
   else  
      printf( "\nCat not found!\n" );  
}  
```  
  
```Output  
cat cow dog goat horse human pig rat  
cat found at 002F0F04  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arama ve sıralama](../../c-runtime-library/searching-and-sorting.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)