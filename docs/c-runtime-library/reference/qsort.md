---
title: qsort | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- qsort
dev_langs:
- C++
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ac444680a22a99f292b1728181103789435a150
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="qsort"></a>qsort

Hızlı sıralama gerçekleştirir. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [qsort_s](qsort-s.md).

## <a name="syntax"></a>Sözdizimi

```C
void qsort(
   void *base,
   size_t num,
   size_t width,
   int (__cdecl *compare )(const void *, const void *)
);
```

### <a name="parameters"></a>Parametreler

*temel* hedef dizi başlangıcı.

*sayı* dizi öğeleri boyutu.

*Genişlik* öğesi boyutunu bayt cinsinden.

*Karşılaştırma* iki dizi öğeleri karşılaştırır ve ilişkilerini belirten bir değer döndüren bir kullanıcı tarafından sağlanan yordam işaretçi.

## <a name="remarks"></a>Açıklamalar

**Qsort** işlevi bir dizi sıralamak için hızlı Sıralama algoritması uygulayan *numarası* öğeleri, her biri *genişliği* bayt sayısı. Bağımsız değişken *temel* sıralanacak dizisinin temel bir işaretçidir. **qsort** sıralanmış öğelerini kullanarak bu dizinin üzerine yazar.

**qsort** çağrıları *karşılaştırmak* rutin bir veya daha fazla kez sıralama sırasında ve işaretçileri iki dizi öğelerinin her çağrıda geçirir.

```C
compare( (void *) & elem1, (void *) & elem2 );
```

Yordam öğeleri karşılaştırır ve aşağıdaki değerlerden birini döndürür.

|İşlev dönüş değeri Karşılaştır|Açıklama|
|-----------------------------------|-----------------|
|< 0|**elem1** değerinden **elem2**|
|0|**elem1** eşdeğer **elem2**|
|> 0|**elem1** büyük **elem2**|

Dizi karşılaştırma işlevi tarafından tanımlandığı şekilde, artan düzende sıralanır. Azalan olarak bir dizi sıralamak için "büyüktür" ve "küçüktür" karşılaştırma işlevinde duygusu ters çevrilir.

Bu işlev parametrelerini doğrular. Varsa *karşılaştırmak* veya *numarası* olan **NULL**, veya *temel* olan **NULL** ve **numarası* sıfır olmayan, olduğundan veya *genişliği* küçük sıfırdan, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, işlevi döndürür ve **errno** ayarlanır **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**qsort**|\<stdlib.h > ve \<search.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
