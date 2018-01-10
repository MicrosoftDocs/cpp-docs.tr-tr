---
title: Abs labs, llabs, _abs64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- abs
- _abs64
- labs
- llabs
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
- stdlib/_abs64
- math/abs
- _abs64
- abs
- labs
- math/labs
- llabs
- math/llabs
- cmath/abs
dev_langs: C++
helpviewer_keywords:
- absolute values
- abs function
- abs64 function
- _abs64 function
- calculating absolute values
ms.assetid: 60f789d1-4a1e-49f5-9e4e-0bdb277ea26a
caps.latest.revision: "29"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 64c09dc8c8ce1ce5493ac4b2515c6b0be2910627
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="abs-labs-llabs-abs64"></a>Abs labs, llabs, _abs64
Bağımsız değişken mutlak değerini hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int abs(   
   int n   
);  
long abs(   
   long n   
);   // C++ only  
long long abs(   
   long long n   
);   // C++ only  
double abs(   
   double n   
);   // C++ only  
long double abs(  
   long double n  
);   // C++ only  
float abs(  
   float n   
);   // C++ only  
long labs(  
   long n   
);  
long long llabs(  
   long long n   
);  
__int64 _abs64(   
   __int64 n   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `n`  
 Sayısal değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `abs`, `labs`, `llabs` Ve `_abs64` işlevleri parametresi mutlak değerini döndür `n`. Döndürülen hata yoktur.  
  
## <a name="remarks"></a>Açıklamalar  
 Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz `abs` alın ve dönüş `long`, `long long`, `float`, `double`, ve `long double` değerleri. Bu aşırı tanımlanan \<cmath > Üstbilgi. Bir C programı `abs` her zaman alır ve bir tamsayı döndürür  
  
 **Microsoft özel**  
  
 Herhangi bir tam sayı türü kullanarak temsil edilebilir negatif tamsayı aralığı türü kullanarak temsil edilebilir pozitif tamsayılar aralığından daha büyük olduğundan dönüştürülemez bu işlevler için bağımsız değişken sağlayın mümkündür. Dönüş türü tarafından bağımsız değişkeni mutlak değerini gösterilemezse `abs` işlevler değişmeden bağımsız değişken değeri döndürür. Özellikle, `abs(INT_MIN)` döndürür `INT_MIN`, `labs(LONG_MIN)` döndürür `LONG_MIN`, `llabs(LLONG_MIN)` döndürür `LLONG_MIN`, ve `_abs64(_I64_MIN)` döndürür `_I64_MIN`. Bunun anlamı `abs` işlevleri, pozitif bir değer güvence altına almak için kullanılamaz.  
  
 **Son Microsoft özel**  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|  
|-------------|-----------------------|---------------------------|  
|`abs`, `labs`, `llabs`|\<Math.h > veya \<stdlib.h >|\<cmath >, \<cstdlib >, \<stdlib.h > veya \<math.h >|  
|`_abs64`|\<stdlib.h >|\<cstdlib > veya \<stdlib.h >|  
  
 Aşırı yüklenmiş sürümlerini `abs` C++'da eklemelisiniz \<cmath > Üstbilgi.  
  
## <a name="example"></a>Örnek  
 Bu program hesaplar ve birkaç sayıların mutlak değerlerini görüntüler.  
  
```C  
// crt_abs.c  
// Build: cl /W3 /TC crt_abs.c  
// This program demonstrates the use of the abs function  
// by computing and displaying the absolute values of  
// several numbers.  
  
#include <stdio.h>  
#include <math.h>  
#include <stdlib.h>  
#include <limits.h>  
  
int main( void )  
{  
    int ix = -4;  
    long lx = -41567L;  
    long long llx = -9876543210LL;  
    __int64 wx = -1;  
  
    // absolute 32 bit integer value  
    printf_s("The absolute value of %d is %d\n", ix, abs(ix));  
  
    // absolute long integer value  
    printf_s("The absolute value of %ld is %ld\n", lx, labs(lx));  
  
    // absolute long long integer value  
    printf_s("The absolute value of %lld is %lld\n", llx, llabs(llx));  
  
    // absolute 64 bit integer value  
    printf_s("The absolute value of 0x%.16I64x is 0x%.16I64x\n", wx,   
        _abs64(wx));  
  
    // Integer error cases:  
    printf_s("Microsoft implementation-specific results:\n");  
    printf_s(" abs(INT_MIN) returns %d\n", abs(INT_MIN));  
    printf_s(" labs(LONG_MIN) returns %ld\n", labs(LONG_MIN));  
    printf_s(" llabs(LLONG_MIN) returns %lld\n", llabs(LLONG_MIN));  
    printf_s(" _abs64(_I64_MIN) returns 0x%.16I64x\n", _abs64(_I64_MIN));  
}  
```  
  
```Output  
The absolute value of -4 is 4  
The absolute value of -41567 is 41567  
The absolute value of -9876543210 is 9876543210  
The absolute value of 0xffffffffffffffff is 0x0000000000000001  
Microsoft implementation-specific results:  
 abs(INT_MIN) returns -2147483648  
 labs(LONG_MIN) returns -2147483648  
 llabs(LLONG_MIN) returns -9223372036854775808  
 _abs64(_I64_MIN) returns 0x8000000000000000  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [_cabs](../../c-runtime-library/reference/cabs.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [imaxabs](../../c-runtime-library/reference/imaxabs.md)