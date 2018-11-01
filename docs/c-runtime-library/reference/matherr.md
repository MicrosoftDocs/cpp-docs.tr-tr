---
title: _matherr
ms.date: 04/05/2018
apiname:
- _matherr
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
apitype: DLLExport
f1_keywords:
- _matherr
- matherr
helpviewer_keywords:
- _matherr function
- matherr function
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
ms.openlocfilehash: 980bf8a14ceace82a76562cc47d353f78dbca582
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445727"
---
# <a name="matherr"></a>_matherr

Matematik hatalarını ele alır.

## <a name="syntax"></a>Sözdizimi

```C
int _matherr( struct _exception * except );
```

### <a name="parameters"></a>Parametreler

*Dışında*<br/>
Hata bilgilerini içeren bir yapıya yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_matherr** bir hata veya başarılı olduğunu belirtmek için sıfır olmayan bir değer belirtmek için 0 değerini döndürür. Varsa **_matherr** döndürür 0, bir hata iletisi görüntülenebilir ve **errno** bir uygun hata değerine ayarlanır. Varsa **_matherr** döndürür sıfır dışında bir değeri, hiçbir hata iletisi görüntülenir ve **errno** değişmeden kalır.

Dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Matherr** işlevi kayan nokta matematik kitaplığı işlevleri tarafından oluşturulan hatalar işler. Bu işlevler çağırma **_matherr** ne zaman bir hata algılandı.

Özel hata işleme için farklı bir tanımını sağlamak **_matherr**. C çalışma zamanı kitaplığı (CRT) dinamik olarak bağlı sürümünü kullanıyorsanız, varsayılan değiştirebilirsiniz **_matherr** rutin istemcisinde kullanıcı tanımlı bir sürümüyle çalıştırılabilir. Bununla birlikte, varsayılan değiştirilemiyor **_matherr** rutin bir DLL istemcisinde CRT DLL.

Matematik yordamında, hata oluştuğunda **_matherr** işaretçisi adlı bir **_exception** yapısı yazın (tanımlanan \<math.h >) bağımsız değişken olarak. **_Exception** yapısı aşağıdaki öğeleri içerir.

```C
struct _exception
{
    int    type;   // exception type - see below
    char*  name;   // name of function where error occurred
    double arg1;   // first argument to function
    double arg2;   // second argument (if any) to function
    double retval; // value to be returned by function
};
```

**Türü** üye matematik hata türünü belirtir. Tanımlanan şu değerlerden biri \<math.h >:

|Makrosu|Açıklama|
|-|-|
**_ETKİ ALANI**|Bağımsız değişken etki alanı hatası
**_SING**|Bağımsız değişken singularity
**_OVERFLOW**|Taşma aralık hatası
**_PLOSS**|Kısmi bir kayıp önemi
**_TLOSS**|Kaybedilmesi önemi
**_UNDERFLOW**|Sonuç gösterilemeyecek kadar çok küçüktür. (Bu durum şu anda desteklenmiyor.)

Yapı üyesi **adı** hataya neden olan işlevin adını içeren bir boş sonlandırılmış dizeye bir işaretçisidir. Yapı üyeleri **arg1** ve **arg2** hataya neden olan değerleri belirtin. Yalnızca tek bir bağımsız değişken verilirse, bu depolanan **arg1**.

Varsayılan dönüş değeri için belirtilen hata **retval**. Dönüş değeri değiştirirseniz, bir hata gerçekten oluşup oluşmadığını belirtmeniz gerekir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_matherr**|\<Math.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_matherr.c
/* illustrates writing an error routine for math
* functions. The error function must be:
*      _matherr
*/

#include <math.h>
#include <string.h>
#include <stdio.h>

int main()
{
    /* Do several math operations that cause errors. The _matherr
     * routine handles _DOMAIN errors, but lets the system handle
     * other errors normally.
     */
    printf( "log( -2.0 ) = %e\n", log( -2.0 ) );
    printf( "log10( -5.0 ) = %e\n", log10( -5.0 ) );
    printf( "log( 0.0 ) = %e\n", log( 0.0 ) );
}

/* Handle several math errors caused by passing a negative argument
* to log or log10 (_DOMAIN errors). When this happens, _matherr
* returns the natural or base-10 logarithm of the absolute value
* of the argument and suppresses the usual error message.
*/
int _matherr( struct _exception *except )
{
    /* Handle _DOMAIN errors for log or log10. */
    if( except->type == _DOMAIN )
    {
        if( strcmp( except->name, "log" ) == 0 )
        {
            except->retval = log( -(except->arg1) );
            printf( "Special: using absolute value: %s: _DOMAIN "
                     "error\n", except->name );
            return 1;
        }
        else if( strcmp( except->name, "log10" ) == 0 )
        {
            except->retval = log10( -(except->arg1) );
            printf( "Special: using absolute value: %s: _DOMAIN "
                     "error\n", except->name );
            return 1;
        }
    }
    printf( "Normal: " );
    return 0;    /* Else use the default actions */
}
```

```Output
Special: using absolute value: log: _DOMAIN error
log( -2.0 ) = 6.931472e-01
Special: using absolute value: log10: _DOMAIN error
log10( -5.0 ) = 6.989700e-01
Normal: log( 0.0 ) = -inf
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
