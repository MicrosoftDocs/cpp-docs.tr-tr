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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 944c512d0102b459afc2924ef7515311e46cd43c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338156"
---
# <a name="rand"></a>rand

Tanınmış ve tamamen tekrarlanabilir bir algoritma kullanarak pseudorandom bir sayı oluşturur. Bu işlevin daha programlı güvenli bir sürümü mevcuttur; [bkz. rand_s](rand-s.md). **Rand** tarafından oluşturulan sayılar şifreleme olarak güvenli değildir. Daha kriptografik olarak güvenli rasgele sayı üretimi için, [rand_s'ı](rand-s.md) veya [ \< ](../../standard-library/random.md)C++ Standart Kitaplığı'nda rasgele>olarak bildirilen işlevleri kullanın.

## <a name="syntax"></a>Sözdizimi

```C
int rand( void );
```

## <a name="return-value"></a>Dönüş Değeri

**rand** yukarıda açıklandığı gibi pseudorandom bir sayı döndürür. Hata iadesi yok.

## <a name="remarks"></a>Açıklamalar

**Rand** işlevi 0 ile **RAND_MAX** aralığında bir psödorandom tamsayı döndürür (32767). Rand'i aramadan önce psödorastgele sayı **rand**üretecisini tohumlamak için [kum](srand.md) işlevini kullanın.

**Rand** işlevi iyi bilinen bir sıra oluşturur ve şifreleme işlevi olarak kullanmak için uygun değildir. Daha kriptografik olarak güvenli rasgele sayı üretimi için, [rand_s'ı](rand-s.md) veya [ \< ](../../standard-library/random.md)C++ Standart Kitaplığı'nda rasgele>olarak bildirilen işlevleri kullanın. **Rand'in** nesi olduğu ve rasgele \<> bu eksiklikleri nasıl giderdi hakkında bilgi için [rand Considered Harmful](https://channel9.msdn.com/Events/GoingNative/2013/rand-Considered-Harmful)başlıklı bu videoya bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Rand**|\<stdlib.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
