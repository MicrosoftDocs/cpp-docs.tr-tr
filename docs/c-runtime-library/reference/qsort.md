---
title: qsort
description: Microsoft C çalışma zamanı hızlı sıralama API 'sini açıklar `qsort`
ms.date: 10/23/2020
api_name:
- qsort
- _o_qsort
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- qsort
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
ms.openlocfilehash: c658ffae69cd662809eb4dac09c06b6a13f4e051
ms.sourcegitcommit: faecabcdd12ff53eb79dc0df193fc3567f2f037c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92639126"
---
# <a name="qsort"></a>qsort

Hızlı bir sıralama gerçekleştirir. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz. [qsort_s](qsort-s.md).

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

*`base`*\
Hedef dizinin başlangıcı.

*`number`*\
Öğelerde dizi boyutu.

*`width`*\
Bayt cinsinden öğe boyutu.

*`compare`*\
İki dizi öğesini karşılaştıran ve ilişkilerini belirten bir değer döndüren kullanıcı tarafından sağlanan bir yordamın işaretçisi.

## <a name="remarks"></a>Açıklamalar

**`qsort`** İşlevi *`number`* , her bayt bir öğe dizisini sıralamak için bir hızlı sıralama algoritması uygular *`width`* . Bağımsız değişkeni, *`base`* sıralanacak dizinin temelini gösteren bir işaretçidir. **`qsort`** sıralanmış öğeleri kullanarak bu dizinin üzerine yazar.

**`qsort`***`compare`* sıralama sırasında yordamı bir veya daha fazla kez çağırır ve her çağrıda işaretçileri iki dizi öğesine geçirir. *`compare`* İki öğenin aynı olduğunu gösteriyorsa, sonuçta elde edilen sıralanmış dizideki sırası belirtilmemiş olur.

```C
compare( (void *) & elem1, (void *) & elem2 );
```

Rutin öğeleri karşılaştırır ve aşağıdaki değerlerden birini döndürür.

|İşlev dönüş değerini Karşılaştır|Açıklama|
|-----------------------------------|-----------------|
|< 0|**`elem1`** küçüktür **`elem2`**|
|0|**`elem1`** eşdeğer **`elem2`**|
|> 0|**`elem1`** Şundan büyüktür **`elem2`**|

Dizi, karşılaştırma işlevi tarafından tanımlanan şekilde artan sırada sıralanır. Bir diziyi azalan sırada sıralamak için karşılaştırma işlevindeki "büyüktür" ve "küçüktür" durumunu ters çevirin.

Bu işlev, parametrelerini doğrular. Veya ise ya da, *`compare`* *`number`* ise veya sıfır değilse ya da **`NULL`** *`base`* **`NULL`** *`number`* *`width`* sıfırdan küçükse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlev döndürür ve **`errno`** olarak ayarlanır **`EINVAL`** .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**`qsort`**|\<stdlib.h> ve \<search.h>|

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

[Arama ve sıralama](../../c-runtime-library/searching-and-sorting.md)\
[`bsearch`](bsearch.md)\
[`_lsearch`](lsearch.md)
