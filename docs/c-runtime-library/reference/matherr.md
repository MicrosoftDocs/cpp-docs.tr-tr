---
description: 'Hakkında daha fazla bilgi edinin: _matherr'
title: _matherr
ms.date: 04/05/2018
api_name:
- _matherr
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _matherr
- matherr
helpviewer_keywords:
- _matherr function
- matherr function
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
ms.openlocfilehash: 406f9fe43ed64b24637f94cc5bf1ef01d4c94567
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299637"
---
# <a name="_matherr"></a>_matherr

Matematik hatalarını işler.

## <a name="syntax"></a>Sözdizimi

```C
int _matherr( struct _exception * except );
```

### <a name="parameters"></a>Parametreler

*kullanıldıkları*<br/>
Hata bilgilerini içeren yapıya yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_matherr** hatayı göstermek için 0, veya başarıyı göstermek için sıfır dışında bir değer döndürür. **_Matherr** 0 döndürürse, bir hata iletisi görüntülenebilir ve **errno** uygun bir hata değerine ayarlanır. **_Matherr** sıfır dışında bir değer döndürürse, hata iletisi gösterilmez ve **errno** değişmeden kalır.

Dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Matherr** işlevi, matematik kitaplığının kayan nokta işlevleri tarafından oluşturulan hataları işler. Bu işlevler bir hata algılandığında **_matherr** çağırır.

Özel hata işleme için **_matherr** farklı bir tanım sağlayabilirsiniz. C çalışma zamanı kitaplığı 'nın (CRT) dinamik olarak bağlı sürümünü kullanıyorsanız, istemci çalıştırılabilirinin varsayılan **_matherr** yordamını Kullanıcı tanımlı bir sürümle değiştirebilirsiniz. Ancak, CRT DLL 'nin bir DLL istemcisinde varsayılan **_matherr** yordamını değiştiremezsiniz.

Matematik yordamında bir hata oluştuğunda, **_matherr** bağımsız değişken olarak bir **_Exception** tür yapısına (içinde tanımlı) bir işaretçi ile çağırılır \<math.h> . **_Exception** yapısı aşağıdaki öğeleri içerir.

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

**Tür** üyesi matematik hatası türünü belirtir. Bu, içinde tanımlanan aşağıdaki değerlerden biridir \<math.h> :

|Makroya|Anlamı|
|-|-|
| **_DOMAIN** | Bağımsız değişken etki alanı hatası |
| **_SING** | Bağımsız değişken Singular |
| **_OVERFLOW** | Taşma aralığı hatası |
| **_PLOSS** | Kısmi anlamlı kaybı |
| **_TLOSS** | Toplam anlam kaybı |
| **_UNDERFLOW** | Sonuç gösterilemeyecek kadar küçük. (Bu durum şu anda desteklenmiyor.) |

Yapı üye **adı** , hataya neden olan işlevin adını içeren, null ile sonlandırılmış bir dizenin bir işaretçisidir. **Arg1** ve **arg2** yapı üyeleri hataya neden olan değerleri belirtir. Yalnızca bir bağımsız değişken verilirse, **arg1** içinde depolanır.

Verilen hata için varsayılan dönüş değeri **retval**' dir. Dönüş değerini değiştirirseniz, bir hatanın gerçekten oluşup oluşmadığını belirtmesi gerekir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_matherr**|\<math.h>|

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

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
