---
title: div | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- div
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
- div
dev_langs:
- C++
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2090ca5e08af74854177f02d6313d6c1304ed2c6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="div"></a>div
Sayının ve iki tamsayı değerleri geri kalanı hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
div_t div(   
   int numer,  
   int denom   
);  
ldiv_t div(  
   long numer,  
   long denom  
); /* C++ only */   
lldiv_t div(  
   long long numer,  
   long long denom  
); /* C++ only */  
```  
  
#### <a name="parameters"></a>Parametreler  
 `numer`  
 Pay.  
  
 `denom`  
 Payda değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `div` tür bağımsız değişkenleri kullanarak adında `int` türü yapısını döndürür `div_t`, sayının ve kalanı oluşur. Aşırı yükleme dönüş değeri türü bağımsız değişkenleri ile `long` olan `ldiv_t`. Her ikisi de `div_t` ve `ldiv_t` STDLIB tanımlanır. H.  
  
## <a name="remarks"></a>Açıklamalar  
 `div` İşlev böler `numer` tarafından `denom` ve böylece sayının ve kalanı hesaplar. [Div_t](../../c-runtime-library/standard-types.md) yapısı içeren sayının `int quot`ve kalan `int rem`. Sayının işaretini, matematiksel sayının aynıdır. Mutlak değerini matematiksel sayının mutlak değerini değerinden en büyük tamsayıdır. Paydanın 0 ise, program bir hata iletisi ile sona erer.  
  
 Tür bağımsız değişkenler almayan aşırı `long` veya `long long` yalnızca C++ kodu için kullanılabilir. Dönüş türü [ldiv_t](../../c-runtime-library/standard-types.md) üyeleri içeren `long quot` ve `long rem`ve dönüş türü [lldiv_t](../../c-runtime-library/standard-types.md) üyeleri içeren `long long quot` ve `long long rem`, aynı olan üyeleri olarak anlamları `div_t`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`div`|\<stdlib.h>|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_div.c  
// arguments: 876 13  
  
// This example takes two integers as command-line  
// arguments and displays the results of the integer  
// division. This program accepts two arguments on the  
// command line following the program name, then calls  
// div to divide the first argument by the second.  
// Finally, it prints the structure members quot and rem.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <math.h>  
  
int main( int argc, char *argv[] )  
{  
   int x,y;  
   div_t div_result;  
  
   x = atoi( argv[1] );  
   y = atoi( argv[2] );  
  
   printf( "x is %d, y is %d\n", x, y );  
   div_result = div( x, y );  
   printf( "The quotient is %d, and the remainder is %d\n",  
           div_result.quot, div_result.rem );  
}  
```  
  
```Output  
x is 876, y is 13  
The quotient is 67, and the remainder is 5  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)