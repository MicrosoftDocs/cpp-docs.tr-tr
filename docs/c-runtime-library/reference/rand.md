---
title: rand | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
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
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aada39e6ea3de3cae65642d29fa1b5ce4bad098e
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="rand"></a>rand

Geçici rastgele bir sayı, iyi bilinen ve tam olarak yeniden üretilebilir bir algoritma kullanarak oluşturur. Bu işlev program aracılığıyla daha güvenli bir sürümü kullanılabilir; bkz: [rand_s](../../c-runtime-library/reference/rand-s.md). Sayı oluşturulan tarafından `rand` şifreleme açısından güvenli değildir. Daha fazla şifreleme açısından güvenli rastgele sayı oluşturma için kullanmak `rand_s` veya İşlevler bildirilen C++ Standart kitaplığında [ \<rastgele >](../../standard-library/random.md).

## <a name="syntax"></a>Sözdizimi

```C
int rand( void );
```

## <a name="return-value"></a>Dönüş Değeri

`rand`Yukarıda açıklanan geçici rastgele bir sayı döndürür. Döndürülen hata yoktur.

## <a name="remarks"></a>Açıklamalar

`rand` İşlevi aralıktaki 0 geçici rastgele bir tamsayı döndürür `RAND_MAX` (32767). Kullanım [srand](../../c-runtime-library/reference/srand.md) çağırmadan önce geçici rastgele sayı oluşturucu çekirdek işlevi `rand`.

`rand` İşlevi iyi bilinen bir sıra oluşturur ve bir şifreleme işlevi olarak kullanmak için uygun değil. Daha fazla şifreleme açısından güvenli rastgele sayı oluşturma için kullanmak `rand_s` veya İşlevler bildirilen C++ Standart kitaplığında [ \<rastgele >](../../standard-library/random.md). Sorun nedir hakkında bilgi için `rand()` ve nasıl `<random>` bu eksik adresleri bkz [bu videoyu](http://go.microsoft.com/fwlink/?LinkId=397615).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`rand`|\<stdlib.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.

## <a name="example"></a>Örnek

```C
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

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)  
[srand](../../c-runtime-library/reference/srand.md)  
[rand_s](../../c-runtime-library/reference/rand-s.md)  