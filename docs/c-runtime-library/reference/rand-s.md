---
title: rand_s
ms.date: 1/02/2018
apiname:
- rand_s
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
ms.openlocfilehash: d196a6f5d7483deb9a7e1b8d7fa929532b6197db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572724"
---
# <a name="rands"></a>rand_s

Sözde rastgele sayı oluşturur. Bu işlevin daha güvenli bir sürümü olduğu [rand](rand.md), açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>Parametreler

*randomValue*<br/>
Oluşturulan değerini tutacak bir tamsayı işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır Aksi takdirde bir hata kodu. Giriş işaretleyicisini _randomValue_ null bir işaretçiyse, işlevi içinde açıklanan şekilde geçersiz parametre işleyicisini çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, işlev döndürür **EINVAL** ve ayarlar **errno** için **EINVAL**. Diğer herhangi bir nedenle için işlev başarısız olursa *_randomValue_ 0 olarak ayarlayın.

## <a name="remarks"></a>Açıklamalar

**Rand_s** işlevi için 0 aralığındaki bir sözde rastgele tamsayı Yazar **uınt_max** Giriş işaretçisi. **Rand_s** işlevi işletim sistemi şifreleme yoluyla güvenli rasgele sayılar üretmek için kullanır. Tarafından oluşturulan çekirdek kullanmaz [srand](srand.md) işlevi, ya da tarafından kullanılan rastgele bir sayı sıra etkilemez [rand](rand.md).

**Rand_s** işlevi gerektirir, sabiti **_CRT_RAND_S** tanımlanmış olması için aşağıdaki örnekte olduğu gibi bildirilen işlev ekleme deyimi önce:

```C
#define _CRT_RAND_S
#include <stdlib.h>
```

**rand_s** bağlıdır [RtlGenRandom](/windows/desktop/api/ntsecapi/nf-ntsecapi-rtlgenrandom) API, yalnızca Windows XP'de kullanılabilir ve desteklenir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**rand_s**|\<stdlib.h >|

Daha fazla bilgi için [Uyumluluk](../../c-runtime-library/compatibility.md).

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
[rand](rand.md)<br/>
[srand](srand.md)<br/>
