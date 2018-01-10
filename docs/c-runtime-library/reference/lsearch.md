---
title: _lsearch | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _lsearch
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
- _lsearch
- lsearch
dev_langs: C++
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ffb2c0ec3547278f048855bb72a2e4ae1bb00287
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="lsearch"></a>_lsearch
Bir değer için doğrusal arama yapar; listenin sonuna ekler bulunamazsa. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *_lsearch(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `key`  
 Aranacak nesne.  
  
 `base`  
 Aranacak dizi tabanı işaretçi.  
  
 `num`  
 Öğe sayısı.  
  
 `width`  
 Her dizi öğesi genişliği.  
  
 `compare`  
 İşaretçi karşılaştırması yordama. İlk parametre anahtar arama için bir işaretçidir. İkinci parametre anahtarla karşılaştırılması gereken bir dizi öğesine bir işaretçidir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Anahtar bulunursa, `_lsearch` dizisi öğesine bir işaretçi döndüren `base` eşleşen `key`. Anahtar bulunamazsa `_lsearch` dizinin sonuna en yeni eklenen öğesine bir işaretçi döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_lsearch` İşlevi gerçekleştiren değeri için doğrusal arama `key` dizisindeki `num` öğeleri, her biri `width` bayt sayısı. Farklı `bsearch`, `_lsearch` sıralanacak dizi gerektirmez. Varsa `key` bulunamadı, `_lsearch` artırır ve dizinin sonuna ekler `num`.  
  
 `compare` Bağımsız değişkeni, iki dizi öğeleri karşılaştırır ve ilişkilerini belirten bir değer döndürür ve kullanıcı tarafından sağlanan bir yordama bir işaretçidir. `_lsearch`çağrıları `compare` işaretçileri iki dizi öğelerinin her çağrıda geçirme, arama sırasında rutin bir veya birden çok kez. `compare`gerekir ve öğeleri karşılaştırma ya da dönüş sıfır olmayan (öğeleri farklı olduğu anlamına gelir) veya 0 (öğeleri aynı olduğu anlamına gelir).  
  
 Bu işlev parametrelerini doğrular. Varsa `compare`, `key` veya `num` olan `NULL`, veya `base` null ve *`num` sıfır olmayan, olduğundan veya `width` küçük sıfırdan, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevi döndürür `NULL`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_lsearch`|\<Search.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_lsearch.c  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( const void *arg1, const void *arg2 );  
  
int main(void)  
{  
   char * wordlist[4] = { "hello", "thanks", "bye" };  
                            // leave room to grow...  
   int n = 3;  
   char **result;  
   char *key = "extra";  
   int i;  
  
   printf( "wordlist before _lsearch:" );  
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );  
   printf( "\n" );  
  
   result = (char **)_lsearch( &key, wordlist,   
                      &n, sizeof(char *), compare );  
  
   printf( "wordlist after _lsearch:" );  
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );  
   printf( "\n" );  
}  
  
int compare(const void *arg1, const void *arg2 )  
{  
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );  
}  
```  
  
```Output  
wordlist before _lsearch: hello thanks bye  
wordlist after _lsearch: hello thanks bye extra  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arama ve sıralama](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)   
 [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)