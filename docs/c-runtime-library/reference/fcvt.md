---
title: _fcvt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _fcvt
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fcvt
dev_langs:
- C++
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: def428073c15f3d408174916098573ddff98cde0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fcvt"></a>_fcvt
Kayan noktalı sayı bir dizeye dönüştürür. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_fcvt(   
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `value`  
 Dönüştürülecek sayı.  
  
 `count`  
 Ondalık basamak sayısı.  
  
 `dec`  
 Saklanan Ondalık ayırıcının konum işaretçi.  
  
 `sign`  
 Depolanan oturum göstergesi işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_fcvt` bir işaretçi bir rakam dizesiyle, hata NULL döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_fcvt` İşlevi kayan noktalı sayı null olarak sonlandırılan bir karakter dizeye dönüştürür. `value` Dönüştürülecek kayan noktalı sayı parametresidir. `_fcvt` rakamı depolar `value` dize olarak ve bir null karakter ('\0') ekler. `count` Parametresi, ondalık ayırıcıdan sonra depolanması için basamak sayısını belirtir. Aşırı basamak yuvarlanır için `count` yerleştirir. Varsa daha az `count` basamaklı duyarlık, dize sıfırlarla doldurulan.  
  
 Toplam tarafından döndürülen basamak sayısı `_fcvt` değil aşacak `_CVTBUFSIZE`.  
  
 Yalnızca rakamlar dizesinde depolanır. Ondalık ayırıcının ve işaretini konumunu `value` yükseltebilmeniz `dec` ve çağrısından sonra oturum açın. `dec` Parametresi tamsayı değerine; işaret bu tamsayı değeri ondalık dizenin başlangıcını göre konumunu sağlar. Sıfır veya negatif tamsayı değeri belirten Ondalık ayırıcının sol tarafında ilk rakam arasındadır. Parametre `sign` işaret işaretini gösteren tamsayı `value`. Tamsayı varsa 0 olarak ayarlanırsa `value` pozitif ve sıfır olmayan bir sayı ise ayarlanır `value` negatiftir.  
  
 Arasındaki farkı `_ecvt` ve `_fcvt` yorumu içinde olduğu `count` parametresi. `_ecvt` Yorumlar `count` toplam çıkış dizesinde basamak sayısı olarak ancak `_fcvt` yorumlar `count` ondalık basamak sayısı.  
  
 `_ecvt` ve `_fcvt` dönüştürme için tek bir statik olarak ayrılan arabellek kullanın. Bu yordamlar her çağrısına önceki çağrısının sonuçlarını bozar.  
  
 Bu işlev parametrelerini doğrular. Varsa `dec` veya `sign` null, veya `count` 0'dır, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve NULL döndürülür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_fcvt`|\<stdlib.h>|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_fcvt.c  
// compile with: /W3  
// This program converts the constant  
// 3.1415926535 to a string and sets the pointer  
// buffer to point to that string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  decimal, sign;  
   char *buffer;  
   double source = 3.1415926535;  
  
   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996  
   // Note: _fcvt is deprecated; consider using _fcvt_s instead  
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",  
            source, buffer, decimal, sign );  
}  
```  
  
```Output  
source: 3.1415926535   buffer: '31415927'   decimal: 1   sign: 0  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)