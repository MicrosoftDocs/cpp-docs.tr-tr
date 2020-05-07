---
title: rand
ms.date: 4/2/2020
api_name:
- rand
- _o_rand
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 8f2a4d00310671e8ba80055e38e479e348562ac2
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919521"
---
# <a name="rand"></a>rand

İyi bilinen ve tamamen tekrarlanabilir bir algoritma kullanarak bir pseudportaıdom numarası üretir. Bu işlevin daha programlı olarak güvenli bir sürümü kullanılabilir; bkz. [rand_s](rand-s.md). **S_SAYI_ÜRET** tarafından oluşturulan sayılar şifreli olarak güvenli değildir. Daha fazla şifreli rastgele sayı oluşturma için [rand_s](rand-s.md) veya C++ standart kitaplığı 'nda belirtilen işlevleri [ \<rastgele>](../../standard-library/random.md)kullanın.

## <a name="syntax"></a>Sözdizimi

```C
int rand( void );
```

## <a name="return-value"></a>Dönüş Değeri

**S_SAYI_ÜRET** , yukarıda açıklandığı gibi pseudportaıdom numarasını döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

**S_SAYI_ÜRET** işlevi, 0 ile **RAND_MAX** (32767) aralığında bir pseudportaıdom tamsayı döndürür. **S_SAYI_ÜRET**çağrılmadan önce pseudportadom-Number üreticisini temel almak için [srand](srand.md) işlevini kullanın.

**S_SAYI_ÜRET** işlevi iyi bilinen bir dizi oluşturur ve şifreleme işlevi olarak kullanım için uygun değildir. Daha fazla şifreli rastgele sayı oluşturma için [rand_s](rand-s.md) veya C++ standart kitaplığı 'nda belirtilen işlevleri [ \<rastgele>](../../standard-library/random.md)kullanın. **S_SAYI_ÜRET** ile ilgili nelerin yanlış olduğu ve rastgele> bu \<eksiklikleri nasıl ele aldığı hakkında bilgi için bkz. [S_sayı_üret 'in zararlı olduğu kabul edilen](https://channel9.msdn.com/Events/GoingNative/2013/rand-Considered-Harmful)bu video.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ran**|\<Stdlib. h>|

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
