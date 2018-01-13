---
title: _matherr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _matherr
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
dev_langs: C++
helpviewer_keywords:
- _matherr function
- matherr function
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1c7aa22479630605279b0d1364317d479bd1eac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="matherr"></a>_matherr
Matematik hataları işler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int _matherr(  
   struct _exception *except   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *dışında*  
 Hata bilgilerini içeren yapısına yönelik işaretçinin.  
  
## <a name="return-value"></a>Dönüş Değeri  
 _**matherr** bir hata veya başarılı olduğunu belirtmek için sıfır olmayan bir değer belirtmek için 0 değerini döndürür. Varsa \_ **matherr** döndürür 0, hata iletisi görüntülenebilir ve `errno` ilgili hata değerine ayarlanır. Varsa \_ **matherr** döndürür sıfır olmayan bir değer, hata iletisi görüntülenir ve `errno` değişmeden kalır.  
  
 Dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 _**Matherr** işlevi math kitaplığı kayan nokta işlevleri tarafından oluşturulan hatalar işler. Bu işlev çağrısı \_ **matherr** ne zaman bir hata algılandı.  
  
 Özel hata işleme için farklı bir _ tanım sağlayabilir**matherr**. C çalışma zamanı kitaplığı (Msvcr90.dll) dinamik olarak bağlı sürümünü kullanıyorsanız, varsayılan değiştirebilirsiniz \_ **matherr** kullanıcı tanımlı bir sürüm ile yürütülebilir bir istemcisindeki rutin. Ancak, varsayılan değiştirilemiyor `_matherr` Msvcr90.dll DLL istemcisini rutin.  
  
 Matematik yordamında _ bir hata meydana geldiğinde**matherr** işaretçi ile adlı bir **_exception** yapısı (Math.h içinde tanımlanmıştır) bağımsız değişken olarak yazın. **_Exception** yapısı aşağıdaki öğeleri içerir.  
  
 **int türü**  
 Özel durum türü.  
  
 **char \*adı**  
 Hatanın oluştuğu işlevin adı.  
  
 **çift arg1**, **arg2**  
 Birinci ve ikinci (varsa) işlev bağımsız değişkenleri.  
  
 **çift retval**  
 İşlev tarafından döndürülen değer.  
  
 **Türü** matematik hata türünü belirtir. Math.h içinde tanımlanan aşağıdaki değerlerden biridir.  
  
 `_DOMAIN`  
 Bağımsız değişken etki alanı hatası.  
  
 `_SING`  
 Bağımsız değişken singularity.  
  
 `_OVERFLOW`  
 Taşma aralık hatası.  
  
 `_PLOSS`  
 Kısmi bir kayıp anlamlı.  
  
 `_TLOSS`  
 Toplam zarar anlamlı.  
  
 `_UNDERFLOW`  
 Sonuç gösterilemeyecek kadar çok küçük. (Bu durum şu anda desteklenmiyor.)  
  
 Yapı üyesi **adı** gösteren bir işaretçidir hatanın nedeni işlevin adını içeren null ile sonlandırılmış bir dize. Yapı üyeleri **arg1** ve **arg2** hataya değerleri belirtin. (Yalnızca tek bir bağımsız değişken verilirse depolanır **arg1**.)  
  
 Varsayılan dönüş değeri için belirli hata: **retval**. Dönüş değeri değiştirirseniz, bir hata gerçekte oluşup oluşmadığını belirtmeniz gerekir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_matherr`|\<Math.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="output"></a>Çıkış  
  
```  
Special: using absolute value: log: _DOMAIN error  
log( -2.0 ) = 6.931472e-001  
Special: using absolute value: log10: _DOMAIN error  
log10( -5.0 ) = 6.989700e-001  
Normal: log( 0.0 ) = -1.#INF00e+000  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)   