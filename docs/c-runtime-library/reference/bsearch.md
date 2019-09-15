---
title: bsearch
ms.date: 11/04/2016
api_name:
- bsearch
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
- bsearch
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch function
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
ms.openlocfilehash: 9e44e85d1c6d73a68da2edd099cdeb6156f9759d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939430"
---
# <a name="bsearch"></a>bsearch

Sıralanmış bir dizide ikili bir arama gerçekleştirir. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz. [bsearch_s](bsearch-s.md).

## <a name="syntax"></a>Sözdizimi

```C
void *bsearch(
   const void *key,
   const void *base,
   size_t num,
   size_t width,
   int ( __cdecl *compare ) (const void *key, const void *datum)
);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak nesne.

*base*<br/>
Arama verileri tabanı işaretçisi.

*sayısından*<br/>
Öğe sayısı.

*Genişlik*<br/>
Öğelerin genişliği.

*Karşılaştır*<br/>
İki öğeyi karşılaştıran geri çağırma işlevi. Birincisi, arama için anahtarın bir işaretçisidir ve ikincisi, anahtarla Karşılaştırılacak dizi öğesine yönelik bir işaretçidir.

## <a name="return-value"></a>Dönüş Değeri

**bsearch** , *temel*tarafından işaret edilen dizide *anahtar* oluşumuna yönelik bir işaretçi döndürür. *Anahtar* bulunamazsa, işlev **null**döndürür. Dizi artan sıralama düzeninde değilse veya aynı anahtarlara sahip yinelenen kayıtlar içeriyorsa, sonuç tahmin edilemez.

## <a name="remarks"></a>Açıklamalar

**Bsearch** işlevi, her bir *Genişlik* baytından oluşan bir dizi *sayı* öğe için bir ikili arama gerçekleştirir. *Taban* değeri, aranacak dizinin temelini gösteren bir işaretçidir ve *anahtar* , aranan değerdir. *Compare* parametresi, istenen anahtarı bir dizi öğesiyle karşılaştıran Kullanıcı tarafından sağlanan yordamın bir işaretçisidir ve ilişkilerini belirten aşağıdaki değerlerden birini döndürür:

|*Compare* yordamının döndürdüğü değer|Açıklama|
|-----------------------------------------|-----------------|
|\< 0|Anahtar, Array öğesinden küçüktür.|
|0|Anahtar, dizi öğesine eşittir.|
|> 0|Anahtar, dizi öğesinden daha büyük.|

Bu işlev, parametrelerini doğrular. *Compare*, *Key* veya *Number* değeri **null**ise veya *taban* **null** ise ve *sayı* sıfır değilse, [parametre doğrulama bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır ](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin veriliyorsa, **errno** olarak `EINVAL` ayarlanır ve işlev **null**değerini döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**bsearch**|\<Stdlib. h > ve \<Search. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program bir dize dizisini qsort ile sıralar ve sonra bsearch kullanarak "Cat" sözcüğünü bulur.

```C
// crt_bsearch.c
#include <search.h>
#include <string.h>
#include <stdio.h>

int compare( char **arg1, char **arg2 )
{
   /* Compare all of both strings: */
   return _strcmpi( *arg1, *arg2 );
}

int main( void )
{
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};
   char **result;
   char *key = "cat";
   int i;

   /* Sort using Quicksort algorithm: */
   qsort( (void *)arr, sizeof(arr)/sizeof(arr[0]), sizeof( char * ), (int (*)(const
   void*, const void*))compare );

   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */
      printf( "%s ", arr[i] );

   /* Find the word "cat" using a binary search algorithm: */
   result = (char **)bsearch( (char *) &key, (char *)arr, sizeof(arr)/sizeof(arr[0]),
                              sizeof( char * ), (int (*)(const void*, const void*))compare );
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
