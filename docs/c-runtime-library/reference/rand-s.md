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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: cad1740e64c7bbda553ac1a6c777d7e2295152ba
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919537"
---
# <a name="rand_s"></a>rand_s

Pseudportaıdom numarası üretir. Bu, güvenlik geliştirmeleri olan [S_SAYI_ÜRET](rand.md)'in daha güvenli bir sürümüdür ve bu [özellik, CRT 'daki güvenlik özelliklerinde](../../c-runtime-library/security-features-in-the-crt.md)açıklanmıştır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>Parametreler

*Rasgeledeğeri*<br/>
Üretilen değeri tutacak bir tamsayıya yönelik bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır, aksi takdirde bir hata kodu. Giriş işaretçisi _rastgele değeri_ null bir işaretçisiyse, Işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, işlev **EINVAL** döndürür ve **errno** 'ı **EINVAL**olarak ayarlar. İşlev başka bir nedenle başarısız olursa, *_Rasgelevalue_ 0 olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**Rand_s** işlevi, giriş işaretçisine **UINT_MAX** için 0 aralığına bir pseudportadom tamsayı yazar. **Rand_s** işlevi, şifreleme güvenli rastgele sayılar oluşturmak için işletim sistemini kullanır. [SRVe](srand.md) işlevi tarafından oluşturulan çekirdeği kullanmaz ve [S_SAYI_ÜRET](rand.md)tarafından kullanılan rastgele sayı sırasını da etkilemez.

**Rand_s** işlevi, aşağıdaki örnekte olduğu gibi, işlevin dahil edilmesi için ekleme ifadesiyle önce sabit **_CRT_RAND_S** tanımlanmasını gerektirir:

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#define _CRT_RAND_S
#include <stdlib.h>
```

**rand_s** , yalnızca Windows XP ve üzeri sürümlerde bulunan [Rtlgenrandom](/windows/win32/api/ntsecapi/nf-ntsecapi-rtlgenrandom) API 'sine bağlıdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**rand_s**|\<Stdlib. h>|

Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
[ran](rand.md)<br/>
[srand](srand.md)<br/>
