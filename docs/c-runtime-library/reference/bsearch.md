---
title: bsearch
ms.date: 11/04/2016
apiname:
- bsearch
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
- bsearch
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch function
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
ms.openlocfilehash: e170ce67d22c0d97825a7eb754546a29daac6d89
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347762"
---
# <a name="bsearch"></a>bsearch

Sıralanmış bir diziyi ikili bir arama gerçekleştirir. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz: [bsearch_s](bsearch-s.md).

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
Temel arama verileri için işaretçi.

*Sayı*<br/>
Öğe sayısı.

*Genişlik*<br/>
Öğe genişliği.

*Karşılaştırma*<br/>
İki öğeyi karşılaştıran bir geri çağırma işlevi. İlk arama anahtarı için bir işaretçidir ve ikinci anahtarı ile Karşılaştırılacak dizi öğesinin işaretçisidir.

## <a name="return-value"></a>Dönüş Değeri

**bsearch** işaretçi döndüren bir olayın oluşmasını *anahtarı* işaret ettiği dizideki *temel*. Varsa *anahtarı* , işlev döndürür bulunamadı **NULL**. Dizi sıralama düzeni artan sırada değil veya yinelenen kayıtları ile özdeş anahtarlarını içeren, sonucu tahmin edilemez.

## <a name="remarks"></a>Açıklamalar

**Bsearch** işlevi gerçekleştiren bir sıralanmış bir diziyi ikili arama *numarası* öğeleri, her biri *genişliği* bayt cinsinden boyutu. *Temel* aranacak, dizinin temel bir işaretçi değeridir ve *anahtar* Aranan değer. *Karşılaştırma* parametresi, bir işaretçi, bir dizi öğesine İstenen anahtar karşılaştırır ve aralarındaki ilişkiyi belirleme aşağıdaki değerlerden birini döndürür ve kullanıcı tarafından sağlanan bir yordama:

|Tarafından döndürülen değer *karşılaştırma* yordamı|Açıklama|
|-----------------------------------------|-----------------|
|\< 0|Anahtar dizi öğesi'dan küçük.|
|0|Anahtar, dizi öğesine eşittir.|
|> 0|Anahtar, dizi öğesi büyüktür.|

Bu işlev, parametrelerini doğrular. Varsa *karşılaştırma*, *anahtarı* veya *numarası* olduğu **NULL**, veya *temel* olduğu **NULL**ve *numarası* sıfır değilse, ya da Eğer *genişliği* sıfır açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır `EINVAL` ve işlev döndürür **NULL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**bsearch**|\<stdlib.h > ve \<search.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program, bir dize dizisi ile qsort sıralar ve ardından "cat" sözcüğü bulmak için bsearch kullanır.

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
