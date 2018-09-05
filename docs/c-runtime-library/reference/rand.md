---
title: rand | Microsoft Docs
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- rand
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
- rand
dev_langs:
- C++
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, generating
- numbers, pseudorandom
- rand function
- pseudorandom numbers
- numbers, generating pseudorandom
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 081e380dc639ed6a814913dd42c6fc1b55041b01
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43681141"
---
# <a name="rand"></a>rand

İyi bilinen ve tam olarak yeniden üretilebilen algoritmasını kullanarak rastgele bir sayı oluşturur. Bu işlevin daha programlı olarak güvenli bir sürümü kullanılabilir; bkz: [rand_s](rand-s.md). Oluşturulmuş sayılara **rand** şifreleme bakımından güvenli değildir. Daha fazla şifreleme yoluyla güvenli rasgele sayı üretimi için kullanmak [rand_s](rand-s.md) veya C++ Standart Kitaplığı'nda bildirilen işlevlerin [ \<rastgele >](../../standard-library/random.md).

## <a name="syntax"></a>Sözdizimi

```C
int rand( void );
```

## <a name="return-value"></a>Dönüş Değeri

**rand** yukarıda açıklandığı bir sözde rastgele sayı döndürür. Döndürülen hata yok.

## <a name="remarks"></a>Açıklamalar

**Rand** işlevi için 0 aralığındaki bir sözde rastgele tamsayı döndürür **RAND_MAX** (32767). Kullanım [srand](srand.md) işlevini çağırmadan önce sözde rastgele sayı üretici temel **rand**.

**Rand** işlevi iyi bilinen bir sıra üretir ve bir şifreleme işlevi olarak kullanılmaya uygun değil. Daha fazla şifreleme yoluyla güvenli rasgele sayı üretimi için kullanmak [rand_s](rand-s.md) veya C++ Standart Kitaplığı'nda bildirilen işlevlerin [ \<rastgele >](../../standard-library/random.md). Sorun nedir hakkında bilgi için **rand** ve nasıl \<rastgele > Bu videoyu başlıklı bkz bu eksiklikleri adresleri [rand kabul zararlı](https://channel9.msdn.com/Events/GoingNative/2013/rand-Considered-Harmful).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**rand**|\<stdlib.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[srand](srand.md)<br/>
[rand_s](rand-s.md)<br/>
