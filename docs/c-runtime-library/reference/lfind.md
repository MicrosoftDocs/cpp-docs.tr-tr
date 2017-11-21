---
title: _lfind | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _lfind
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
- lfind
- _lfind
dev_langs: C++
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f883aa9f17c8272335a91ebf333e050888be8257
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="lfind"></a>_lfind
Belirtilen anahtar için doğrusal arama gerçekleştirir. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [_lfind_s](../../c-runtime-library/reference/lfind-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *_lfind(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `key`  
 Aranacak nesne.  
  
 `base`  
 Arama veri tabanı işaretçi.  
  
 `num`  
 Dizi öğe sayısı.  
  
 `width`  
 Dizi öğeleri kalınlığı.  
  
 `compare`  
 İşaretçi karşılaştırması yordama. İlk parametre arama için anahtar bir işaretçidir. İkinci parametre anahtarı ile Karşılaştırılacak dizi öğesi bir işaretçidir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Anahtar bulunursa, `_lfind` dizisi öğesine bir işaretçi döndüren `base` eşleşen `key`. Anahtar bulunamazsa `_lfind` döndürür `NULL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_lfind` İşlevi gerçekleştiren değeri için doğrusal arama `key` dizisindeki `num` öğeleri, her biri `width` bayt sayısı. Farklı `bsearch`, `_lfind` sıralanacak dizi gerektirmez. `base` Bağımsız değişkeni bir işaretçidir aranacağı dizinin tabanı. `compare` Bağımsız değişkeni bir işaretçidir iki dizi öğeleri karşılaştırır ve ilişkilerini belirten bir değer döndüren bir kullanıcı tarafından sağlanan yordam. `_lfind`çağrıları `compare` işaretçileri iki dizi öğelerinin her çağrıda geçirme, arama sırasında rutin bir veya birden çok kez. `compare` Yordamı öğeleri karşılaştırır ve (öğeleri farklı olduğu anlamına gelir) sıfır olmayan bir değer döndürür veya 0 (öğeleri aynı olduğu anlamına gelir).  
  
 Bu işlev parametrelerini doğrular. Varsa `compare`, `key` veya `num` olan `NULL`, veya `base` null ve *`num` sıfır olmayan, olduğundan veya `width` küçük sıfırdan, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevi döndürür `NULL`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_lfind`|\<Search.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_lfind.c  
// This program uses _lfind to search a string array  
// for an occurrence of "hello".  
  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare(const void *arg1, const void *arg2 )  
{  
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );  
}  
  
int main( )  
{  
   char *arr[] = {"Hi", "Hello", "Bye"};  
   int n = sizeof(arr) / sizeof(char*);  
   char **result;  
   char *key = "hello";  
  
   result = (char **)_lfind( &key, arr,   
                      &n, sizeof(char *), compare );  
  
   if( result )  
      printf( "%s found\n", *result );  
   else  
      printf( "hello not found!\n" );  
}  
```  
  
```Output  
Hello found  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arama ve sıralama](../../c-runtime-library/searching-and-sorting.md)   
 [_lfind_s](../../c-runtime-library/reference/lfind-s.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)