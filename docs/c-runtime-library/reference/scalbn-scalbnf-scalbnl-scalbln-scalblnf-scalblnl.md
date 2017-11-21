---
title: scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- scalblnl
- scalbnl
- scalbnf
- scalblnf
- scalbn
- scalbln
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- scalblnf
- scalbnl
- scalblnl
- scalbln
- scalbn
- scalbnf
dev_langs: C++
helpviewer_keywords:
- scalbn function
- scalbln function
- scalblnl function
- scalbnl function
- scalbnf function
- scalblnf function
ms.assetid: df2f1543-8e39-4af4-a5cf-29307e64807d
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4c447569279f57226b44b79b3fd22f60c2a30e70
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl"></a>scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl
Kayan noktalı sayı bir tam sayı flt_radıx gücünü tarafından çarpar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double scalbn(  
   double x,  
   int exp   
);  
float scalbn(  
   float x,  
   int exp  
);  // C++ only  
long double scalbn(  
   long double x,  
   int exp  
);  // C++ only   
float scalbnf(  
   float x,  
   int exp  
);   
long double scalbnl(  
   long double x,  
   int exp  
);  
double scalbln(  
   double x,  
   long exp   
);  
float scalbln(  
   float x,  
   long exp  
);  // C++ only  
long double scalbln(  
   long double x,  
   long exp  
);  // C++ only   
float scalblnf(  
   float x,  
   long exp  
);   
long double scalblnl(  
   long double x,  
   long exp  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `x`  
 Kayan nokta değeri.  
  
 `exp`  
 Tamsayı üs.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `scalbn` İşlevleri dönüş değerini `x`  *  `FLT_RADIX` <sup>exp</sup> başarılı olduğunda. Taşma (işaretini bağlı olarak `x`), `scalbn` döndürür `HUGE_VAL`; `errno` değeri ayarı `ERANGE`.  
  
 Hakkında daha fazla bilgi için `errno` ve dönüş değerleri için bkz: olası hata [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `FLT_RADIX`tanımlanan \<float.h > yerel kayan noktalı sayı tabanını olarak; ikili sistemlerde, 2 ' değerine sahip ve `scalbn` eşdeğerdir [ldexp](../../c-runtime-library/reference/ldexp.md).  
  
 Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz `scalbn` ve `scalbln` alın ve dönüş `float` veya `long double` türleri. C programı `scalbn` her zaman alan bir `double` ve bir `int` ve döndürür bir `double`, ve `scalbln` her zaman alan bir `double` ve `long` ve döndürür bir `double`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`scalbn`, `scalbnf`, `scalbnl`, `scalbln`, `scalblnf`, `scalblnl`|\<Math.h >|\<cmath >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_scalbn.c  
// Compile using: cl /W4 crt_scalbn.c  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 6.4, y;  
   int p = 3;  
  
   y = scalbn( x, p );  
   printf( "%2.1f times FLT_RADIX to the power of %d is %2.1f\n", x, p, y );  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
6.4 times FLT_RADIX to the power of 3 is 51.2  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [modf, modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)