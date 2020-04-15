---
title: qsort
ms.date: 4/2/2020
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 09de57e206eb6fd4a75a0a9444332136aeee0e9d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338256"
---
# <a name="qsort"></a>qsort

Hızlı bir sıralama gerçekleştirir. Bu işlevin daha güvenli bir sürümü mevcuttur; [bkz qsort_s](qsort-s.md).

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
Hedef dizinin başlangıcı.

*number*<br/>
Öğelerdeki dizi boyutu.

*genişlik*<br/>
Baytlarda eleman boyutu.

*Karşılaştırmak*<br/>
İki dizi öğesini karşılaştıran ve ilişkilerini belirten bir değer döndüren, kullanıcı tarafından sağlanan yordamı işaretçi.

## <a name="remarks"></a>Açıklamalar

**Qsort** işlevi, *her genişlik* baytı olan *bir dizi sayı* öğesini sıralamak için hızlı sıralama algoritması uygular. Bağımsız değişken *tabanı,* sıralanacak dizi tabanına işaretçidir. **qsort** sıralanmış öğeleri kullanarak bu dizi üzerine yazar.

**qsort** sıralama sırasında rutin bir veya daha fazla kez *karşılaştırma* çağırır ve işaretçileri her aramada iki dizi öğesine geçirir.

```C
compare( (void *) & elem1, (void *) & elem2 );
```

Yordam öğeleri karşılaştırır ve aşağıdaki değerlerden birini döndürür.

|Fonksiyon iade değerini karşılaştırma|Açıklama|
|-----------------------------------|-----------------|
|< 0|**elem1** **elem2** daha az|
|0|**elem1** **elem2** eşdeğeri|
|> 0|**elem1** **elem2'den** büyük|

Dizi, karşılaştırma işlevi tarafından tanımlandığı gibi, artan sırada sıralanır. Bir diziyi azalan sırada sıralamak için, karşılaştırma işlevindeki "büyükten büyük" ve "küçük" sözcük lerini tersine çevirin.

Bu işlev parametrelerini doğrular. *Karşılaştırma* veya *sayı* **NULL**ise veya *taban* **NULL** ise ve *sayı* sıfır değilse veya *genişlik* sıfırdan küçükse, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, işlev döndürür ve **errno** **EINVAL**olarak ayarlanır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**qsort**|\<stdlib.h> \<ve search.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
