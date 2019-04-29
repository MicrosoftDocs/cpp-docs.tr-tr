---
title: qsort
ms.date: 11/04/2016
apiname:
- qsort
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- qsort
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
ms.openlocfilehash: 8a770965a03e43227b99f122924c723691f79c61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358105"
---
# <a name="qsort"></a>qsort

Hızlı sıralama gerçekleştirir. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz: [qsort_s](qsort-s.md).

## <a name="syntax"></a>Sözdizimi

```C
void qsort(
   void *base,
   size_t number,
   size_t width,
   int (__cdecl *compare )(const void *, const void *)
);
```

### <a name="parameters"></a>Parametreler

*base*<br/>
Hedef dizi başlangıcı.

*Sayı*<br/>
Öğeleri dizi boyutu.

*Genişlik*<br/>
Öğe boyutunu bayt cinsinden.

*Karşılaştırma*<br/>
Kullanıcı tarafından sağlanan iki diziyi öğe karşılaştırır ve bunların belirten bir değeri döndüren bir yordam için işaretçi.

## <a name="remarks"></a>Açıklamalar

**Qsort** işlevi uygulayan bir dizi sıralamak için hızlı Sıralama algoritması *numarası* öğeleri, her biri *genişliği* bayt. Bağımsız değişken *temel* sıralanacak dizinin temel bir işaretçisidir. **qsort** sıralanmış öğelerini kullanarak bu dizinin üzerine yazar.

**qsort** çağrıları *karşılaştırma* rutin bir veya daha fazla zaman sıralama sırasında ve işaretçileri iki dizi öğelerine her çağrıda geçirir.

```C
compare( (void *) & elem1, (void *) & elem2 );
```

Yordam, öğeleri karşılaştırır ve aşağıdaki değerlerden birini döndürür.

|İşlev dönüş değeri karşılaştırın|Açıklama|
|-----------------------------------|-----------------|
|< 0|**elem1** küçüktür **elem2**|
|0|**elem1** eşdeğer **elem2**|
|> 0|**elem1** büyüktür **elem2**|

Dizi karşılaştırma işlevi tarafından tanımlandığı şekilde, artan düzende sıralanır. Azalan olarak bir diziyi sıralamak için "büyüktür" ve "az" karşılaştırma işlevde anlamı ters çevir.

Bu işlev, parametrelerini doğrular. Varsa *karşılaştırmak* veya *numarası* olan **NULL**, veya *temel* olan **NULL** ve *numarası* sıfır değilse, ya da Eğer *genişliği* küçük sıfırdan, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, işlev döndürür ve **errno** ayarlanır **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**qsort**|\<stdlib.h > ve \<search.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_qsort.c
// arguments: every good boy deserves favor

/* This program reads the command-line
* parameters and uses qsort to sort them. It
* then displays the sorted arguments.
*/

#include <stdlib.h>
#include <string.h>
#include <stdio.h>

int compare( const void *arg1, const void *arg2 );

int main( int argc, char **argv )
{
   int i;
   /* Eliminate argv[0] from sort: */
   argv++;
   argc--;

   /* Sort remaining args using Quicksort algorithm: */
   qsort( (void *)argv, (size_t)argc, sizeof( char * ), compare );

   /* Output sorted list: */
   for( i = 0; i < argc; ++i )
      printf( " %s", argv[i] );
   printf( "\n" );
}

int compare( const void *arg1, const void *arg2 )
{
   /* Compare all of both strings: */
   return _stricmp( * ( char** ) arg1, * ( char** ) arg2 );
}
```

```Output
boy deserves every favor good
```

## <a name="see-also"></a>Ayrıca bkz.

[Arama ve Sıralama](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch](bsearch.md)<br/>
[_lsearch](lsearch.md)<br/>
