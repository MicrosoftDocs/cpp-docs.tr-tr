---
title: kalan, remainderf, remainderl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- remainderl
- remainder
- remainderf
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
- remainderf
- remainder
- remainderl
dev_langs:
- C++
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2b7a5d55fd079f03338a6860755a783ba4d82b76
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl
Sayının yakın tamsayı değerine yuvarlanan iki kayan nokta değerlerinin kalanı hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double remainder(   
   double numer,  
   double denom  
);  
float remainder(   
   float numer,  
   float denom  
); /* C++ only */  
long double remainder(   
   long double numer,  
   long double denom  
); /* C++ only */  
float remainderf(   
   float numer,  
   float denom  
);  
long double remainderl(   
   long double numer,  
   long double denom  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `numer`  
 Pay.  
  
 `denom`  
 Payda değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Kayan nokta geri kalanı `x`  /  `y`. Varsa değerini `y` 0.0, olan `remainder` sessiz NaN döndürür. Sessiz NaN tarafından gösterimini hakkında bilgi için `printf` ailesi, bkz: [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `remainder` İşlevi kayan nokta kalanı hesaplar `r` , `x`  /  `y` şekilde `x`  =  `n`  *  `y`  +  `r`, burada `n` tamsayı değeri'en yakın olan `x`  /  `y` ve `n` olsa bile her &#124; `n`  -  `x`  /  `y` &#124; 1/2 =. Zaman `r` = 0, `r` aynı işarete sahip `x`.  
  
 Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz `remainder` alın ve dönüş `float` veya `long double` değerleri. Bir C programı `remainder` her zaman iki double alır ve bir double döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`remainder`, `remainderf`, `remainderl`|\<Math.h >|  
  
 Uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_remainder.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
  
   z = remainder(w, x);  
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);  
}  
```  
  
```Output  
The remainder of -10.00 / 3.00 is -1.000000  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)