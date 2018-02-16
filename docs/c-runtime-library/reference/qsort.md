---
title: qsort | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a39f6edf9dfdf2130bfe9d00cc2a9453f48ad9f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="qsort"></a>qsort
Hızlı sıralama gerçekleştirir. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [qsort_s](../../c-runtime-library/reference/qsort-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void qsort(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(const void *, const void *)   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `base`  
 Hedef dizi başlangıcı.  
  
 `num`  
 Öğeleri dizi boyutu.  
  
 `width`  
 Öğe boyutunu bayt cinsinden.  
  
 `compare`  
 Kullanıcı tarafından sağlanan iki dizi öğeleri karşılaştırır ve ilişkilerini belirten bir değer döndüren bir yordam işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 `qsort` İşlevi bir dizi sıralamak için hızlı Sıralama algoritması uygulayan `num` öğeleri, her biri `width` bayt sayısı. Bağımsız değişken `base` sıralanacak dizisinin temel bir işaretçidir. `qsort` Bu dizi sıralanmış öğeleri kullanarak geçersiz kılar.  
  
 `qsort` çağrıları `compare` rutin bir veya daha fazla kez sıralama sırasında ve işaretçileri iki dizi öğelerinin her çağrıda geçirir.  
  
```  
compare( (void *) & elem1, (void *) & elem2 );  
```  
  
 Yordam öğeleri karşılaştırır ve aşağıdaki değerlerden birini döndürür.  
  
|İşlev dönüş değeri Karşılaştır|Açıklama|  
|-----------------------------------|-----------------|  
|< 0|`elem1` Küçüktür `elem2`|  
|0|`elem1` Eşdeğer `elem2`|  
|> 0|`elem1` Büyüktür `elem2`|  
  
 Dizi karşılaştırma işlevi tarafından tanımlandığı şekilde, artan düzende sıralanır. Azalan olarak bir dizi sıralamak için "büyüktür" ve "küçüktür" karşılaştırma işlevinde duygusu ters çevrilir.  
  
 Bu işlev parametrelerini doğrular. Varsa `compare` veya `num` olan `NULL`, veya `base` olan `NULL` ve *`num` sıfır olmayan, olduğundan veya `width` küçük sıfırdan, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, işlevi döndürür ve `errno` ayarlanır `EINVAL`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`qsort`|\<stdlib.h > ve \<search.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arama ve sıralama](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)