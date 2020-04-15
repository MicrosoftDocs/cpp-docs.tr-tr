---
title: bsearch_s
ms.date: 4/2/2020
api_name:
- bsearch_s
- _o_bsearch_s
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: ef8a68f0db45e718af6b17fe0d08c33a6fd61d6c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333840"
---
# <a name="bsearch_s"></a>bsearch_s

Sıralanmış bir dizinin ikili araması yapar. Bu işlev, [CRT'deki Güvenlik özelliklerinde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmeleriyle birlikte [bsearch'ün](bsearch.md) bir sürümüdür.

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

*Anahtar*\
Aranacak anahtara işaretçi.

*Temel*\
Arama verilerinin tabanına işaretçi.

*Numarası*\
Öğe sayısı.

*Genişlik*\
Öğelerin genişliği.

*Karşılaştırmak*\
İki öğeyi karşılaştıran geri arama işlevi. İlk bağımsız değişken *bağlam* işaretçisidir. İkinci bağımsız değişken, arama *anahtarına* işaretçidir. Üçüncü bağımsız *değişken, anahtarla*karşılaştırılması gereken dizi öğesine işaretçidir.

*Bağlam*\
Karşılaştırma işlevinde erişilebilen bir nesneye işaretçi.

## <a name="return-value"></a>Döndürülen değer

**bsearch_s,** *baza*işaret edilen dizideki *bir anahtar* oluşumuna işaret eder. *Anahtar* bulunamazsa, işlev **NULL döndürür.** Dizi artan sıralama sırasına sahip değilse veya aynı anahtarlara sahip yinelenen kayıtlar içeriyorsa, sonuç öngörülemez.

Geçersiz parametreler işleve aktarılırsa, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev **NULL**döndürür. Daha fazla bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

### <a name="error-conditions"></a>Hata koşulları

|||||||
|-|-|-|-|-|-|
|*anahtar*|*base*|*Karşılaştırmak*|*number*|*genişlik*|**Errno**|
|**Null**|herhangi bir|herhangi bir|herhangi bir|herhangi bir|**Eınval**|
|herhangi bir|**Null**|herhangi bir|!= 0|herhangi bir|**Eınval**|
|herhangi bir|herhangi bir|herhangi bir|herhangi bir|= 0|**Eınval**|
|herhangi bir|herhangi bir|**Null**|a|herhangi bir|**Eınval**|

## <a name="remarks"></a>Açıklamalar

**bsearch_s** işlevi, her biri *genişlik* baytboyutunda sıralanmış bir *sayı* öğesi dizisinin ikili aramasını gerçekleştirir. *Temel* değer aranacak dizinin tabanına işaretçidir ve *anahtar* aranan değerdir. *Karşılaştırma* parametresi, istenen anahtarı bir dizi öğesiyle karşılaştıran ve ilişkilerini belirten aşağıdaki değerlerden birini döndüren kullanıcı tarafından sağlanan yordamın işaretçisidir:

|*Karşılaştırma* yordamı ile döndürülen değer|Açıklama|
|-----------------------------------------|-----------------|
|\<0|Anahtar dizi öğesinden daha azdır.|
|0|Anahtar dizi öğesine eşittir.|
|> 0|Anahtar dizi öğesinden daha büyüktür.|

Aranan veri yapısı bir nesnenin parçasıysa ve karşılaştırma işlevinin nesnenin üyelerine erişmesi gerekiyorsa *bağlam* işaretçisi yararlı olabilir. *Karşılaştırma* işlevi, geçersiz işaretçiyi uygun nesne türüne ve bu nesnenin üyelerine erişebilir. *Bağlam* parametresinin eklenmesi, verileri *karşılaştırma* işlevine kullanılabilir hale getirmek için statik değişkenlerin kullanılmasıyla ilişkili yeniden canlandırma hatalarını önlemek için ek bağlam kullanılabildiğinden, **bsearch_s** daha güvenli hale getirir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**bsearch_s**|\<stdlib.h> \<ve search.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Bu program [qsort_s](qsort-s.md)ile bir dize dizi sini sıralar ve daha sonra "kedi" sözcüğü bulmak için bsearch_s kullanır.

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

[Arama ve Sıralama](../../c-runtime-library/searching-and-sorting.md)\
[_lfind](lfind.md)\
[_lsearch](lsearch.md)\
[qsort](qsort.md)
