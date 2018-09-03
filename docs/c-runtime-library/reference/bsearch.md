---
title: bsearch | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- bsearch
dev_langs:
- C++
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch function
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77d7576b5e8914148a8c67d8df82573c1f379e16
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394700"
---
# <a name="bsearch"></a>bsearch

İkili arama sıralanmış bir dizinin gerçekleştirir. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [bsearch_s](bsearch-s.md).

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

*Anahtarı*<br/>
Aranacak nesne.

*base*<br/>
Arama verilerini temel işaretçi.

*Sayı*<br/>
Öğe sayısı.

*Genişlik*<br/>
Öğe genişliği.

*Karşılaştırma*<br/>
İki öğe karşılaştırır geri çağırma işlevi. İlk arama için anahtar için bir işaretçi ve ikinci anahtar ile Karşılaştırılacak dizi öğesi için bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**bsearch** işaretçi için bir örneğini döndüren *anahtar* gösterdiği dizideki *temel*. Varsa *anahtar* , işlevi döndürür bulunamadı **NULL**. Dizi artan sıralama değil veya yinelenen kayıtları aynı anahtarlarla içeriyorsa, öngörülemeyen bir sonucudur.

## <a name="remarks"></a>Açıklamalar

**Bsearch** işlevi gerçekleştiren bir ikili arama sıralanmış bir dizi *numarası* öğeleri, her biri *genişliği* bayt cinsinden boyutu. *Temel* aranacak, dizi tabanı için bir işaretçi bir değerdir ve *anahtar* Aranan değerdir. *Karşılaştırmak* parametredir bir işaretçi bir dizi öğesine istenen anahtarına karşılaştırır ve ilişkilerini belirterek aşağıdaki değerlerden birini döndürür ve kullanıcı tarafından sağlanan bir yordama:

|Tarafından döndürülen değer *karşılaştırmak* yordamı|Açıklama|
|-----------------------------------------|-----------------|
|\< 0|Dizi öğesi değerinden anahtardır.|
|0|Anahtar dizi öğesine eşittir.|
|> 0|Dizi öğesi büyük anahtardır.|

Bu işlev parametrelerini doğrular. Varsa *karşılaştırmak*, *anahtar* veya *numarası* olan **NULL**, veya *temel* olan **NULL**ve **numarası* sıfır olmayan, olduğundan veya *genişliği* sıfır açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlevi döndürür **NULL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**bsearch**|\<stdlib.h > ve \<search.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program bir dize dizisi qsort ile sıralar ve "kat" word bulmak için bsearch kullanır.

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
