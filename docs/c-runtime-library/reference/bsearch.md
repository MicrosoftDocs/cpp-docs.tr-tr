---
title: bsearch
ms.date: 4/2/2020
api_name:
- bsearch
- _o_bsearch
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
- bsearch
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch function
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
ms.openlocfilehash: efad391eb2512cfa59cc3597430a84727676f27e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333799"
---
# <a name="bsearch"></a>bsearch

Sıralanmış bir dizinin ikili araması yapar. Bu işlevin daha güvenli bir sürümü mevcuttur; [bkz. bsearch_s](bsearch-s.md).

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

*Anahtar*\
Aranacak anahtara işaretçi.

*Temel*\
Arama verilerinin tabanına işaretçi.

*Numarası*\
Öğe sayısı.

*Genişlik*\
Öğelerin genişliği.

*Karşılaştırmak*\
İki öğeyi karşılaştıran geri arama işlevi. İlkarama için anahtar için bir işaretçi ve ikinci anahtar ile karşılaştırıldığında dizi öğesi için bir işaretçi.

## <a name="return-value"></a>Döndürülen değer

**bsearch,** *baza*işaret edilen dizideki *bir anahtar* oluşumuna işaret eden bir işaretçi döndürür. *Anahtar* bulunamazsa, işlev **NULL döndürür.** Dizi artan sıralama sırasına sahip değilse veya aynı anahtarlara sahip yinelenen kayıtlar içeriyorsa, sonuç öngörülemez.

## <a name="remarks"></a>Açıklamalar

**bsearch** işlevi, her bir *genişlik* baytboyutunda sıralanmış *sayı* öğeleri dizisinin ikili aramasını gerçekleştirir. *Temel* değer aranacak dizinin tabanına işaretçidir ve *anahtar* aranan değerdir. *Karşılaştırma* parametresi, istenen anahtarı bir dizi öğesiyle karşılaştıran kullanıcı tarafından sağlanan bir yordamın işaretçisidir. İlişkilerini belirten aşağıdaki değerlerden birini döndürür:

|*Karşılaştırma* yordamı ile döndürülen değer|Açıklama|
|-----------------------------------------|-----------------|
|\<0|Anahtar dizi öğesinden daha azdır.|
|0|Anahtar dizi öğesine eşittir.|
|> 0|Anahtar dizi öğesinden daha büyüktür.|

Bu işlev parametrelerini doğrular. *Karşılaştırma*, *anahtar* veya *sayı* **NULL**ise, veya *temel* **NULL** ve *sayı* sıfır değilse veya *genişlik* sıfır ise, işlev [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağırır. Yürütme devam etmesine izin verilirse, **errno** ayarlanır `EINVAL` ve işlev **NULL**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**bsearch**|\<stdlib.h> \<ve search.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Bu program qsort ile bir dize dizi sini sıralar ve sonra "kedi" sözcüğlerini bulmak için bsearch kullanır.

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

[Arama ve Sıralama](../../c-runtime-library/searching-and-sorting.md)\
[_lfind](lfind.md)\
[_lsearch](lsearch.md)\
[qsort](qsort.md)
