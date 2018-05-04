---
title: rand_s | Microsoft Docs
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, cryptographically secure
- random numbers, generating
- rand_s function
- numbers, pseudorandom
- cryptographically secure random numbers
- pseudorandom numbers
- numbers, generating pseudorandom
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8407848db8f442324127df8d7267a5350c077b2f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="rands"></a>rand_s

Geçici rastgele bir sayı oluşturur. Bu işlev daha güvenli bir sürümü olan [rand](rand.md), açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>Parametreler

*randomValue*<br/>
Tamsayı üretilen değer tutmak için bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, sıfır Aksi takdirde bir hata kodu. Varsa Giriş işaretçisi _randomValue_ null işaretçi açıklandığı gibi bir geçersiz parametre işleyicisi işlevi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, işlevi döndürür **EINVAL** ve ayarlar **errno** için **EINVAL**. İşlev diğer herhangi bir nedenden dolayı başarısız olursa *_randomValue_ 0 olarak ayarlayın.

## <a name="remarks"></a>Açıklamalar

**Rand_s** işlevi aralıktaki 0 geçici rastgele bir tamsayı Yazar **uınt_max** Giriş işaretçisine. **Rand_s** işlevi şifreleme açısından güvenli rastgele sayılar oluşturmak için işletim sistemi kullanır. Tarafından oluşturulan çekirdek kullanmaz [srand](srand.md) işlevi veya tarafından kullanılan rastgele sayı dizisi etkilemez [rand](rand.md).

**Rand_s** işlevi gerektiren bu sabiti **_CRT_RAND_S** tanımlanması ekleme deyimi aşağıdaki örnekteki bildirilmesi için işlev için önce:

```C
#define _CRT_RAND_S
#include <stdlib.h>
```

**rand_s** bağlıdır [RtlGenRandom](http://msdn.microsoft.com/library/windows/desktop/aa387694) kullanılabilir Windows XP ve üstü yalnızca API.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**rand_s**|\<stdlib.h >|

Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
