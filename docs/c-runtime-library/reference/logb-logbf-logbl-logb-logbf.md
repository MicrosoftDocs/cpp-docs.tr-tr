---
title: logb, logbf, logbl, _logb, _logbf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- logb
- _logb
- _logbl
- logbf
- logbl
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
- logb
- logbl
- _logb
- _logbf
- logbf
dev_langs: C++
helpviewer_keywords:
- _logbf function
- mantissas, floating-point variables
- logbf function
- _logb function
- exponent, floating-point numbers
- logbl function
- logb function
- floating-point functions
- floating-point functions, mantissa and exponent
- exponents and mantissas
ms.assetid: 780c4daa-6fe6-4fbc-9412-4c1ba1a1766f
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 81d44f12b363cf74efd334e8ff7daadb4fee5036
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="logb-logbf-logbl-logb-logbf"></a>logb, logbf, logbl, _logb, _logbf
Kayan nokta bağımsız değişkenin üs değeri ayıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double logb(  
   double x   
);  
float logb(  
   float x   
); // C++ only  
long double logb(  
   long double x   
); // C++ only   
float logbf(  
   float x   
);  
long double logbl(  
   long double x   
);  
double _logb(  
   double x   
);  
float _logbf(  
   float x   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 x  
 Kayan nokta değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `logb`taraflı olmayan üs değerini döndürür `x` bir kayan nokta değeri olarak gösterilen imzalı bir tamsayı olarak.  
  
## <a name="remarks"></a>Açıklamalar  
 `logb` İşlevleri üstel kayan nokta bağımsız değişkeninin değerini ayıklamak `x`, gibi `x` sonsuz aralığıyla temsil. Varsa bağımsız değişkeni `x` olan normalleştirilmiş gibi normal dışı, işlem görür.  
  
 Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz `logb` alın ve dönüş `float` veya `long double` değerleri. Bir C programı `logb` her zaman alan ve döndüren bir `double`.  
  
|Giriş|SEH özel durumu|Matherr özel durumu|  
|-----------|-------------------|-----------------------|  
|± QNAN, UL|Yok.|_DOMAIN|  
|± 0|ZERODIVIDE|_SING|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_logb`|\<float.h >|  
|`logb`, `logbf`, `logbl`, `_logbf`|\<Math.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)