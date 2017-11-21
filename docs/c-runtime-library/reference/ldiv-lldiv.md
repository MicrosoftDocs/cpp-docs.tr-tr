---
title: ldiv, lldiv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ldiv
- lldiv
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
- ldiv
- lldiv
dev_langs: C++
helpviewer_keywords:
- ldiv function
- lldiv function
- quotients, computing
- computing remainders
- remainder computing
- computing quotients
ms.assetid: 68ab5d83-27a4-479c-9d52-d055eb139eca
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1c1da38d40c45ecd6dc36eed594304894a25dcc7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ldiv-lldiv"></a>ldiv, lldiv
İki tamsayının geri kalanı ve sayının bir işlem olarak hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
ldiv_t ldiv(  
   long numer,  
   long denom   
);  
lldiv_t lldiv(  
   long long numer,  
   long long denom   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `numer`  
 Pay.  
  
 `denom`  
 Payda değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `ldiv`bir yapı türü döndürür [ldiv_t](../../c-runtime-library/standard-types.md) sayının ve kalanı oluşur. `lldiv`bir yapı türü döndürür [lldiv_t](../../c-runtime-library/standard-types.md) sayının ve kalanı oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 `ldiv` Ve `lldiv` işlevleri bölmek `numer` tarafından `denom`ve böylece sayının ve geri kalan işlem. Sayının işaretini, matematiksel sayının aynıdır. Sayının mutlak değerini matematiksel sayının mutlak değerini değerinden en büyük tamsayıdır. Paydanın 0 ise, program bir hata iletisi ile sona erer. `ldiv`ve `lldiv` aynı `div`dışında bağımsız değişkenleri `ldiv` ve döndürülen yapısı üyeleri türü tümü `long`ve bağımsız değişkenleri `lldiv` ve döndürülen yapısı tür üyesi `long long`.  
  
 `ldiv_t` Ve `lldiv_t` yapıları tanımlanmış \<stdlib.h >.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`ldiv`, `lldiv`|\<stdlib.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_ldiv.c  
  
#include <stdlib.h>  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   long x = 5149627, y = 234879;  
   ldiv_t div_result;  
  
   div_result = ldiv( x, y );  
   printf( "For %ld / %ld, the quotient is ", x, y );  
   printf( "%ld, and the remainder is %ld\n",   
            div_result.quot, div_result.rem );  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
For 5149627 / 234879, the quotient is 21, and the remainder is 217168  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [div](../../c-runtime-library/reference/div.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)