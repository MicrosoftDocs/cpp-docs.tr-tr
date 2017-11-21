---
title: bsearch | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: bsearch
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
f1_keywords: bsearch
dev_langs: C++
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch function
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2a7166570785d2d73db06fcdf7e42492317621a0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bsearch"></a>bsearch
İkili arama sıralanmış bir dizinin gerçekleştirir. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [bsearch_s](../../c-runtime-library/reference/bsearch-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *bsearch(   
   const void *key,  
   const void *base,  
   size_t num,  
   size_t width,  
   int ( __cdecl *compare ) (const void *key, const void *datum)   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `key`  
 Aranacak nesne.  
  
 `base`  
 Arama verilerini temel işaretçi.  
  
 `num`  
 Öğe sayısı.  
  
 `width`  
 Öğe genişliği.  
  
 `compare`  
 İki öğe karşılaştırır geri çağırma işlevi. İlk arama için anahtar için bir işaretçi ve ikinci anahtar ile Karşılaştırılacak dizi öğesi için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `bsearch`İşaretçi için bir örneğini döndüren `key` gösterdiği dizideki `base`. Varsa `key` , işlevi döndürür bulunamadı `NULL`. Dizi artan sıralama değil veya yinelenen kayıtları aynı anahtarlarla içeriyorsa, öngörülemeyen bir sonucudur.  
  
## <a name="remarks"></a>Açıklamalar  
 `bsearch` İşlevi gerçekleştiren bir ikili arama sıralanmış bir dizi `num` öğeleri, her biri `width` bayt cinsinden boyutu. `base` Aranacak, dizi tabanı için bir işaretçi bir değerdir ve `key` Aranan değerdir. `compare` Parametresi, bir dizi öğesine istenen anahtarına karşılaştırır ve ilişkilerini belirterek aşağıdaki değerlerden birini döndürür ve kullanıcı tarafından sağlanan bir yordama bir işaretçidir:  
  
|Tarafından döndürülen değer `compare` yordamı|Açıklama|  
|-----------------------------------------|-----------------|  
|\< 0|Dizi öğesi değerinden anahtardır.|  
|0|Anahtar dizi öğesine eşittir.|  
|> 0|Dizi öğesi büyük anahtardır.|  
  
 Bu işlev parametrelerini doğrular. Varsa `compare`, `key` veya `num` olan `NULL`, veya `base` olan `NULL` ve *`num` sıfır olmayan, olduğundan veya `width` sıfır anlatıldığıgibigeçersizparametreişleyicisiçağrılır[Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevi döndürür `NULL`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`bsearch`|\<stdlib.h > ve \<search.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Bu program bir dize dizisi qsort ile sıralar ve "kat" word bulmak için bsearch kullanır.  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arama ve sıralama](../../c-runtime-library/searching-and-sorting.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)