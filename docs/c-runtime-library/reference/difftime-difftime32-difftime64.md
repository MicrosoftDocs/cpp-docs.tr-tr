---
title: difftime, _difftime32, _difftime64
ms.date: 4/2/2020
api_name:
- _difftime32
- difftime
- _difftime64
- _o__difftime32
- _o__difftime64
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _difftime64
- difftime
- difftime64
- _difftime32
- difftime32
helpviewer_keywords:
- _difftime32 function
- difftime function
- time, finding the difference
- difftime64 function
- _difftime64 function
- difftime32 function
ms.assetid: 4cc0ac2b-fc7b-42c0-8283-8c9d10c566d0
ms.openlocfilehash: e8d9ed3e33935c8e6c788380c02b9ae179dd06e8
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914787"
---
# <a name="difftime-_difftime32-_difftime64"></a>difftime, _difftime32, _difftime64

İki zaman arasındaki farkı bulur.

## <a name="syntax"></a>Sözdizimi

```C
double difftime( time_t timeEnd, time_t timeStart );
double _difftime32( __time32_t timeEnd, __time32_t timeStart );
double _difftime64( __time64_t timeEnd, __time64_t timeStart );
```

### <a name="parameters"></a>Parametreler

*timeEnd*<br/>
Bitiş zamanı.

*timeStart*<br/>
Başlangıç zamanı.

## <a name="return-value"></a>Dönüş Değeri

**difftime** , *TimeStart* 'dan *timeend*'e kadar geçen süreyi saniye cinsinden döndürür. Döndürülen değer çift duyarlıklı kayan noktalı bir sayıdır. Dönüş değeri 0 olabilir ve bir hata olduğunu gösterir.

## <a name="remarks"></a>Açıklamalar

**Difftime** Işlevi, *TimeStart* ve *timeend*olmak üzere iki sağlanan zaman değeri arasındaki farkı hesaplar.

Sağlanan zaman değeri **time_t**aralığı içinde olmalıdır. **time_t** , 64 bitlik bir değerdir. Bu nedenle, aralığın sonu 18 Ocak 2038, UTC 'den 23:59:59, 31 Aralık 3000 ' 23:59:59 ten uzatılmıştır. **Time_t** alt aralığı hala gece yarısı, 1 Ocak 1970 ' dir.

**difftime** , **_USE_32BIT_TIME_T** tanımlanmış olup olmadığına bağlı olarak **_difftime32** veya **_difftime64** değerlendiren bir satır içi işlevdir. _difftime32 ve _difftime64, zaman türünün belirli bir boyutunun kullanımını zorlamak için doğrudan kullanılabilir.

Bu işlevler, parametrelerini doğrular. Parametrelerden biri sıfır veya negatif ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler 0 döndürür ve **errno** , **EINVAL**olarak ayarlanır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**difftime**|\<Time. h>|
|**_difftime32**|\<Time. h>|
|**_difftime64**|\<Time. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```cpp
// crt_difftime.c
// This program calculates the amount of time
// needed to do a floating-point multiply 100 million times.
//

#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <float.h>

double RangedRand( float range_min, float range_max)
{
   // Generate random numbers in the half-closed interval
   // [range_min, range_max). In other words,
   // range_min <= random number < range_max
   return ((double)rand() / (RAND_MAX + 1) * (range_max - range_min)
            + range_min);
}

int main( void )
{
   time_t   start, finish;
   long     loop;
   double   result, elapsed_time;
   double   arNums[3];

   // Seed the random-number generator with the current time so that
   // the numbers will be different every time we run.
   srand( (unsigned)time( NULL ) );

   arNums[0] = RangedRand(1, FLT_MAX);
   arNums[1] = RangedRand(1, FLT_MAX);
   arNums[2] = RangedRand(1, FLT_MAX);
   printf( "Using floating point numbers %.5e %.5e %.5e\n", arNums[0], arNums[1], arNums[2] );

   printf( "Multiplying 2 numbers 100 million times...\n" );

   time( &start );
   for( loop = 0; loop < 100000000; loop++ )
      result = arNums[loop%3] * arNums[(loop+1)%3];
   time( &finish );

   elapsed_time = difftime( finish, start );
   printf( "\nProgram takes %6.0f seconds.\n", elapsed_time );
}
```

```Output
Using random floating point numbers 1.04749e+038 2.01482e+038 1.72737e+038
Multiplying 2 floating point numbers 100 million times...
Program takes      3 seconds.
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
