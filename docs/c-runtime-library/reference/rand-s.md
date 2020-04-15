---
title: rand_s
ms.date: 4/2/2020
api_name:
- rand_s
- _o_rand_s
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- rand_s
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, cryptographically secure
- random numbers, generating
- rand_s function
- numbers, pseudorandom
- cryptographically secure random numbers
- pseudorandom numbers
- numbers, generating pseudorandom
ms.openlocfilehash: b11a40dd9dc58964df77330767a55aa95a179319
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338199"
---
# <a name="rand_s"></a>rand_s

Pseudorandom bir sayı oluşturur. Bu işlev [rand](rand.md)daha güvenli bir sürümüdür , [CRT Güvenlik Özellikleri](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmeleri ile.

## <a name="syntax"></a>Sözdizimi

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>Parametreler

*randomValue*<br/>
Oluşturulan değeri tutmak için bir tamsayı için bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Sıfır başarılı, aksi takdirde, bir hata kodu. Giriş işaretçisi _randomValue_ null işaretçisi ise, işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre işleyicisi çağırır. Yürütmedevam etmesine izin verilirse, işlev **EINVAL** döndürür ve **EINVAL** **için errno** ayarlar. İşlev başka bir nedenle başarısız olursa, *_randomValue_ 0 olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**rand_s** işlevi, giriş işaretçisine 0 ile **UINT_MAX** aralığında bir psödorasgele tamsayı yazar. **rand_s** işlevi, şifreleme yle güvenli rasgele sayılar oluşturmak için işletim sistemini kullanır. Kum [fonksiyonu](srand.md) tarafından oluşturulan tohum kullanmaz, ne de [rand](rand.md)tarafından kullanılan rasgele sayı dizisi etkilemez.

**rand_s** işlevi, aşağıdaki örnekte olduğu gibi, işlevin bildirilmesi için dahil etme deyiminden önce sabit **_CRT_RAND_S** tanımlanmasını gerektirir:

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#define _CRT_RAND_S
#include <stdlib.h>
```

**rand_s** [RtlGenRandom](/windows/win32/api/ntsecapi/nf-ntsecapi-rtlgenrandom) API bağlıdır, hangi sadece Windows XP ve daha sonra mevcuttur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**rand_s**|\<stdlib.h>|

Daha fazla bilgi için [Uyumluluk'a](../../c-runtime-library/compatibility.md)bakın.

## <a name="example"></a>Örnek

```C
// crt_rand_s.c
// This program illustrates how to generate random
// integer or floating point numbers in a specified range.

// Remembering to define _CRT_RAND_S prior
// to inclusion statement.
#define _CRT_RAND_S

#include <stdlib.h>
#include <stdio.h>
#include <limits.h>

int main( void )
{
    int             i;
    unsigned int    number;
    double          max = 100.0;
    errno_t         err;

    // Display 10 random integers in the range [ 1,10 ].
    for( i = 0; i < 10;i++ )
    {
        err = rand_s( &number );
        if (err != 0)
        {
            printf_s("The rand_s function failed!\n");
        }
        printf_s( "  %u\n", (unsigned int) ((double)number /
                       ((double) UINT_MAX + 1 ) * 10.0) + 1);
    }

    printf_s("\n");

    // Display 10 random doubles in [0, max).
    for (i = 0; i < 10;i++ )
    {
        err = rand_s( &number );
        if (err != 0)
        {
            printf_s("The rand_s function failed!\n");
        }
        printf_s( "  %g\n", (double) number /
                          ((double) UINT_MAX + 1) * max );
    }
}
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
10
4
5
2
8
2
5
6
1
1

32.6617
29.4471
11.5413
6.41924
20.711
60.2878
61.0094
20.1222
80.9192
65.0712
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Rand](rand.md)<br/>
[srand](srand.md)<br/>
