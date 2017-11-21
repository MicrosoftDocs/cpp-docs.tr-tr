---
title: rand | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: rand
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
f1_keywords: rand
dev_langs: C++
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, generating
- numbers, pseudorandom
- rand function
- pseudorandom numbers
- numbers, generating pseudorandom
ms.assetid: 75d9df25-7aaf-4a88-b940-2775559634e8
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d2ab87437c64525b6d0888ead9fecc773335caf0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="rand"></a>rand
Geçici rastgele bir sayı oluşturur. Bu işlev daha güvenli bir sürümü kullanılabilir, bkz: [rand_s](../../c-runtime-library/reference/rand-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int rand( void );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `rand`Yukarıda açıklanan geçici rastgele bir sayı döndürür. Döndürülen hata yoktur.  
  
## <a name="remarks"></a>Açıklamalar  
 `rand` İşlevi aralıktaki 0 geçici rastgele bir tamsayı döndürür `RAND_MAX` (32767). Kullanım [srand](../../c-runtime-library/reference/srand.md) çağırmadan önce geçici rastgele sayı oluşturucu çekirdek işlevi `rand`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`rand`|\<stdlib.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_rand.c  
// This program seeds the random-number generator  
// with the time, then exercises the rand function.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <time.h>  
  
void SimpleRandDemo( int n )  
{  
   // Print n random numbers.  
   int i;  
   for( i = 0; i < n; i++ )  
      printf( "  %6d\n", rand() );  
}  
  
void RangedRandDemo( int range_min, int range_max, int n )  
{  
   // Generate random numbers in the half-closed interval  
   // [range_min, range_max). In other words,  
   // range_min <= random number < range_max  
   int i;  
   for ( i = 0; i < n; i++ )  
   {  
      int u = (double)rand() / (RAND_MAX + 1) * (range_max - range_min)  
            + range_min;  
      printf( "  %6d\n", u);  
   }  
}  
  
int main( void )  
{  
   // Seed the random-number generator with the current time so that  
   // the numbers will be different every time we run.  
   srand( (unsigned)time( NULL ) );  
  
   SimpleRandDemo( 10 );  
   printf("\n");  
   RangedRandDemo( -100, 100, 10 );  
}  
```  
  
```Output  
22036  
18330  
11651  
27464  
18093  
 3284  
11785  
14686  
11447  
11285  
  
   74  
   48  
   27  
   65  
   96  
   64  
   -5  
  -42  
  -55  
   66  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [srand](../../c-runtime-library/reference/srand.md)   
 [rand_s](../../c-runtime-library/reference/rand-s.md)