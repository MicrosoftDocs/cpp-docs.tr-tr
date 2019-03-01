---
title: bsearch_s
ms.date: 11/04/2016
apiname:
- bsearch_s
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- bsearch_s
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch_s function
ms.assetid: d5690d5e-6be3-4f1d-aa0b-5ca6dbded276
ms.openlocfilehash: 56c5fa45a9d8f9ac9b22474601934d3994da55e4
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210958"
---
# <a name="bsearchs"></a>bsearch_s

Sıralanmış bir diziyi ikili bir arama gerçekleştirir. Bu sürümü olduğu [bsearch](bsearch.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

*anahtar*<br/>
Aranacak nesne.

*base*<br/>
Temel arama verileri için işaretçi.

*Sayı*<br/>
Öğe sayısı.

*Genişlik*<br/>
Öğe genişliği.

*Karşılaştırma*<br/>
İki öğeyi karşılaştıran bir geri çağırma işlevi. İlk bağımsız değişken *bağlam* işaretçi. İkinci bağımsız değişkeni bir işaretçisidir *anahtar* arama. Üçüncü bağımsız değişkeni ile Karşılaştırılacak dizi öğesinin işaretçisidir *anahtar*.

*Bağlam*<br/>
Karşılaştırma işlev erişilebilen bir nesne için bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**bsearch_s** işaretçi döndüren bir olayın oluşmasını *anahtarı* işaret ettiği dizideki *temel*. Varsa *anahtarı* , işlev döndürür bulunamadı **NULL**. Dizi sıralama düzeni artan sırada değil veya yinelenen kayıtları ile özdeş anahtarlarını içeren, sonucu tahmin edilemez.

Geçersiz parametreler bir işleve geçirilirse açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **NULL**. Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Hata koşulları

|||||||
|-|-|-|-|-|-|
|*anahtar*|*base*|*Karşılaştırma*|*Sayı*|*Genişlik*|**errno**|
|**NULL**|Tüm|Tüm|Tüm|Tüm|**EINVAL**|
|Tüm|**NULL**|Tüm|!= 0|Tüm|**EINVAL**|
|Tüm|Tüm|Tüm|Tüm|= 0|**EINVAL**|
|Tüm|Tüm|**NULL**|Bir|Tüm|**EINVAL**|

## <a name="remarks"></a>Açıklamalar

**Bsearch_s** işlevi gerçekleştiren bir sıralanmış bir diziyi ikili arama *numarası* öğeleri, her biri *genişliği* bayt cinsinden boyutu. *Temel* aranacak, dizinin temel bir işaretçi değeridir ve *anahtar* Aranan değer. *Karşılaştırma* parametresi, bir işaretçi, bir dizi öğesine İstenen anahtar karşılaştırır ve aralarındaki ilişkiyi belirleme aşağıdaki değerlerden birini döndürür ve kullanıcı tarafından sağlanan bir yordama:

|Tarafından döndürülen değer *karşılaştırma* yordamı|Açıklama|
|-----------------------------------------|-----------------|
|\< 0|Anahtar dizi öğesi'dan küçük.|
|0|Anahtar, dizi öğesine eşittir.|
|> 0|Anahtar, dizi öğesi büyüktür.|

*Bağlam* Aranan veri yapısı bir nesne bir parçasıdır ve karşılaştırma işlevi nesne üyeleri erişmesi işaretçi yararlı olabilir. *Karşılaştırma* işlevi uygun nesne türü ve erişim üyeleri o nesnenin void işaretçisine dönüştürme. Ek *bağlam* parametreyi yapar **bsearch_s** ek bağlam verileri kullanılabilir hale getirmek için statik değişkenler kullanmayla ilişkili yeniden giriş hataları önlemek için kullanılabilir olduğundan daha güvenli *karşılaştırma* işlevi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**bsearch_s**|\<stdlib.h > ve \<search.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program bir dize dizisi ile sıralar [qsort_s](qsort-s.md)ve ardından "cat" sözcüğü bulunacak bsearch_s kullanır.

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

[Arama ve Sıralama](../../c-runtime-library/searching-and-sorting.md)<br/>
[_lfind](lfind.md)<br/>
[_lsearch](lsearch.md)<br/>
[qsort](qsort.md)<br/>
