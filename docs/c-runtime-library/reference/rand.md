---
title: rand
ms.date: 01/02/2018
api_name:
- rand
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
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- rand
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, generating
- numbers, pseudorandom
- rand function
- pseudorandom numbers
- numbers, generating pseudorandom
ms.openlocfilehash: 6042ab917083cf4131c16012b84afbbe43a7d834
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949548"
---
# <a name="rand"></a>rand

İyi bilinen ve tamamen tekrarlanabilir bir algoritma kullanarak bir pseudportaıdom numarası üretir. Bu işlevin daha programlı olarak güvenli bir sürümü kullanılabilir; bkz. [rand_s](rand-s.md). **S_SAYI_ÜRET** tarafından oluşturulan sayılar şifreli olarak güvenli değildir. Daha fazla şifreli rastgele sayı üretimi için, [rand_s](rand-s.md) veya C++ [ \<](../../standard-library/random.md)standart kitaplıkta belirtilen işlevleri rastgele > kullanın.

## <a name="syntax"></a>Sözdizimi

```C
int rand( void );
```

## <a name="return-value"></a>Dönüş Değeri

**S_SAYI_ÜRET** , yukarıda açıklandığı gibi pseudportaıdom numarasını döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

**S_SAYI_ÜRET** işlevi, 0 ile **RAND_MAX** (32767) aralığında bir pseudportaıdom tamsayı döndürür. **S_SAYI_ÜRET**çağrılmadan önce pseudportadom-Number üreticisini temel almak için [srand](srand.md) işlevini kullanın.

**S_SAYI_ÜRET** işlevi iyi bilinen bir dizi oluşturur ve şifreleme işlevi olarak kullanım için uygun değildir. Daha fazla şifreli rastgele sayı üretimi için, [rand_s](rand-s.md) veya C++ [ \<](../../standard-library/random.md)standart kitaplıkta belirtilen işlevleri rastgele > kullanın. **S_SAYI_ÜRET** ile ilgili nelerin yanlış olduğu ve rastgele > Bu \<eksiklikleri nasıl ele aldığı hakkında bilgi için bkz. [S_SAYI_ÜRET 'in zararlı olduğu kabul edilen](https://channel9.msdn.com/Events/GoingNative/2013/rand-Considered-Harmful)bu video.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**rand**|\<Stdlib. h >|

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
