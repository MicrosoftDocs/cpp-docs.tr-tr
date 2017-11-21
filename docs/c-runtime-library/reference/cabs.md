---
title: _cabs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _cabs
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
- cabsl
- _cabs
- _cabsl
dev_langs: C++
helpviewer_keywords:
- cabs function
- cabsl function
- absolute values
- _cabsl function
- _cabs function
- calculating absolute values
ms.assetid: fea292ee-1a39-4a0a-b416-4a189346ff26
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 53325fe2409a9a09b7d0698a81e1ef9c2a9176d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cabs"></a>_cabs
Karmaşık bir sayının mutlak değerini hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double _cabs(   
   struct _complex z   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `z`  
 Karmaşık sayı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_cabs`başarılı olursa, bağımsız değişkeni mutlak değerini döndürür. Taşma, `_cabs` döndürür `HUGE_VAL` ve ayarlar `errno` için `ERANGE`. Hata ile işleme değiştirebileceğiniz [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_cabs` İşlevi karmaşık türü yapısını olması gereken sayının mutlak değerini hesaplar [_complex](../../c-runtime-library/standard-types.md). Yapı `z` gerçek bir bileşeninin oluşur `x` ve sanal bir bileşeni `y`. Çağrı `_cabs` , ifade için eşdeğer bir değer üreten `sqrt( z.x * z.x + z.y * z.y )`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_cabs`|\<Math.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_cabs.c  
/* Using _cabs, this program calculates  
 * the absolute value of a complex number.  
 */  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct _complex number = { 3.0, 4.0 };  
   double d;  
  
   d = _cabs( number );  
   printf( "The absolute value of %f + %fi is %f\n",  
           number.x, number.y, d );  
}  
```  
  
```Output  
The absolute value of 3.000000 + 4.000000i is 5.000000  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [Abs labs, llabs, _abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   