---
title: __min | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- __min
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
- __min
- min
- _min
dev_langs:
- C++
helpviewer_keywords:
- __min macro
- min macro
- minimum macro
- _min macro
ms.assetid: 2037f26c-b48a-4a69-8870-22519f052a3c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8e4f282331caaef9b56d1ca0b52ebf7c5e63ab6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="min"></a>__min
İki değerden daha küçük veya döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
type __min(  
   type a,  
   type b   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `type`  
 Herhangi bir sayısal veri türü.  
  
 `a, b`  
 Karşılaştırılacak herhangi bir sayısal tür değerleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Küçük iki bağımsız değişken.  
  
## <a name="remarks"></a>Açıklamalar  
 `__min` Makrosu iki değeri karşılaştırır ve daha küçük bir değer döndürür. Bağımsız değişken veri türü, imzalı veya imzasız herhangi sayı olabilir. Bağımsız değişkenleri ve dönüş değeri aynı veri türünde olmalıdır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`__min`|\<stdlib.h>|  
  
## <a name="example"></a>Örnek  
  
```  
// crt_minmax.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int a = 10;  
   int b = 21;  
  
   printf( "The larger of %d and %d is %d\n",  a, b, __max( a, b ) );  
   printf( "The smaller of %d and %d is %d\n", a, b, __min( a, b ) );  
}  
```  
  
```Output  
The larger of 10 and 21 is 21  
The smaller of 10 and 21 is 10  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [__max](../../c-runtime-library/reference/max.md)