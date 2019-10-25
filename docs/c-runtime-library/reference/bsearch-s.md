---
title: bsearch_s
ms.date: 10/22/2019
api_name:
- bsearch_s
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
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- bsearch_s
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch_s function
ms.assetid: d5690d5e-6be3-4f1d-aa0b-5ca6dbded276
ms.openlocfilehash: fc86576dbbe73f63da6bf0e28e7166ef7c552e55
ms.sourcegitcommit: 0a5518fdb9d87fcc326a8507ac755936285fcb94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72811150"
---
# <a name="bsearch_s"></a>bsearch_s

Sıralanmış bir dizide ikili bir arama gerçekleştirir. Bu işlev, [CRT 'Deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [bsearch](bsearch.md) 'ün bir sürümüdür.

## <a name="syntax"></a>Sözdizimi

```C
void *bsearch_s(
   const void *key,
   const void *base,
   size_t number,
   size_t width,
   int ( __cdecl *compare ) ( void *, const void *key, const void *datum),
   void * context
);
```

### <a name="parameters"></a>Parametreler

*anahtar* \
Aranacak anahtarın işaretçisi.

*temel*\
Arama verilerinin tabanına yönelik işaretçi.

*sayı*\
Öğe sayısı.

*genişlik*\
Öğelerin genişliği.

\ *Karşılaştır*
İki öğeyi karşılaştıran geri çağırma işlevi. İlk bağımsız değişken *bağlam* işaretçisidir. İkinci bağımsız değişken, arama için *anahtarın* bir işaretçisidir. Üçüncü bağımsız değişken, *anahtar*ile Karşılaştırılacak dizi öğesine yönelik bir işaretçidir.

*bağlam*\
Karşılaştırma işlevinde erişilebilen nesneye yönelik bir işaretçi.

## <a name="return-value"></a>Dönüş değeri

**bsearch_s** , *temel*tarafından işaret edilen dizide *anahtar* oluşumuna yönelik bir işaretçi döndürür. *Anahtar* bulunamazsa, işlev **null**döndürür. Dizi artan sıralama düzeninde değilse veya aynı anahtarlara sahip yinelenen kayıtlar içeriyorsa, sonuç tahmin edilemez.

İşleve geçersiz parametreler geçirilmemişse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **null**değerini döndürür. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Hata koşulları

|||||||
|-|-|-|-|-|-|
|*anahtar*|*base*|*Karşılaştır*|*sayısından*|*Genişlik*|**errno**|
|**DEĞER**|Kaydedilmemiş|Kaydedilmemiş|Kaydedilmemiş|Kaydedilmemiş|**EıNVAL**|
|Kaydedilmemiş|**DEĞER**|Kaydedilmemiş|! = 0|Kaydedilmemiş|**EıNVAL**|
|Kaydedilmemiş|Kaydedilmemiş|Kaydedilmemiş|Kaydedilmemiş|= 0|**EıNVAL**|
|Kaydedilmemiş|Kaydedilmemiş|**DEĞER**|Kızılötesi|Kaydedilmemiş|**EıNVAL**|

## <a name="remarks"></a>Açıklamalar

**Bsearch_s** işlevi, her bir *Genişlik* baytından oluşan *sayı* öğeleri sıralanmış bir dizi öğe için ikili arama gerçekleştirir. *Taban* değeri, aranacak dizinin temelini gösteren bir işaretçidir ve *anahtar* , aranan değerdir. *Compare* parametresi, istenen anahtarı bir dizi öğesiyle karşılaştıran Kullanıcı tarafından sağlanan yordamın bir işaretçisidir ve ilişkilerini belirten aşağıdaki değerlerden birini döndürür:

|*Compare* yordamının döndürdüğü değer|Açıklama|
|-----------------------------------------|-----------------|
|\< 0|Anahtar, Array öğesinden küçüktür.|
|0|Anahtar, dizi öğesine eşittir.|
|> 0|Anahtar, dizi öğesinden daha büyük.|

Arama veri yapısı nesnenin bir parçasıysa *bağlam* işaretçisi yararlı olabilir ve karşılaştırma işlevinin nesnenin üyelerine erişmesi gerekir. *Compare* işlevi, void işaretçisini uygun nesne türüne ve bu nesnenin üyelerine verebilir. *Bağlam* parametresinin eklenmesi, verileri *karşılaştırma* işlevine uygun hale getirmek için statik değişkenleri kullanmayla ilişkili hataların yeniden oluşmasını önlemek için **bsearch_s** daha güvenli hale getirir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**bsearch_s**|\<Stdlib. h > ve \<Search. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program, [qsort_s](qsort-s.md)içeren bir dize dizisini sıralar ve sonra da "Cat" sözcüğünü bulmak için bsearch_s kullanır.

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[Arama ve sıralama](../../c-runtime-library/searching-and-sorting.md)\
[_lfind](lfind.md)\
[_lsearch](lsearch.md)\
[qsort](qsort.md)
