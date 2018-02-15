---
title: _ecvt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ecvt
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
- _ecvt
dev_langs:
- C++
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee37eb3623f27f4fb6883b2d16fc4c21c2a960c1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ecvt"></a>_ecvt
Dönüştüren bir `double` dizeye sayı. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_ecvt(   
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
 Depolanan basamak sayısı.  
  
 `dec`  
 Ondalık noktasının konumunu depolanır.  
  
 `sign`  
 Dönüştürülen sayısının işareti.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_ecvt` bir işaretçi basamak dizesi olarak döndürür; Bir hata oluştuysa NULL.  
  
## <a name="remarks"></a>Açıklamalar  
 `_ecvt` İşlevi bir karakter dizesi kayan noktalı sayı dönüştürür. `value` Dönüştürülecek kayan noktalı sayı parametresidir. Bu işlev kadar saklar `count` rakamı `value` dize olarak ve bir null karakter ('\0') ekler. Varsa basamak sayısı `value` aşıyor `count`, düşük düzey basamaklı yuvarlanır. Varsa daha az `count` basamak, dize sıfırlarla doldurulan.  
  
 Toplam tarafından döndürülen basamak sayısı `_ecvt` değil aşacak `_CVTBUFSIZE`.  
  
 Yalnızca rakamlar dizesinde depolanır. Ondalık ayırıcının ve işaretini konumunu `value` yükseltebilmeniz `dec` ve `sign` çağrısından sonra. `dec` Parametresi dizenin başlangıcını göre Ondalık ayırıcının konumunu vermiş bir tamsayı değeri işaret eder. 0 veya eksi tamsayı değeri, Ondalık ayırıcının ilk rakam solunda kalan gösterir. `sign` Parametresi işaret dönüştürülen sayının işaretini gösteren bir tamsayı. Tamsayı değer 0 ise, pozitif bir sayıdır. Aksi takdirde, negatif sayısıdır.  
  
 Arasındaki farkı `_ecvt` ve `_fcvt` yorumu içinde olduğu `count` parametresi. `_ecvt` Yorumlar `count` toplam çıkış dizesinde basamak sayısı olarak ancak `_fcvt` yorumlar `count` ondalık basamak sayısı.  
  
 `_ecvt` ve `_fcvt` dönüştürme için tek bir statik olarak ayrılan arabellek kullanın. Bu yordamlar her çağrısına önceki çağrının sonucu bozar.  
  
 Bu işlev parametrelerini doğrular. Varsa `dec` veya `sign` null, veya `count` 0'dır, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve NULL döndürülür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_ecvt`|\<stdlib.h>|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_ecvt.c  
// compile with: /W3  
// This program uses _ecvt to convert a  
// floating-point number to a character string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int     decimal,   sign;  
   char    *buffer;  
   int     precision = 10;  
   double  source = 3.1415926535;  
  
   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996  
   // Note: _ecvt is deprecated; consider using _ecvt_s instead  
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",  
           source, buffer, decimal, sign );  
}  
```  
  
```Output  
source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)