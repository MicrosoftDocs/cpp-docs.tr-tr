---
title: Matematik sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.constants
dev_langs:
- C++
helpviewer_keywords:
- M_PI constant
- M_PI_2 constant
- math constants
- M_2_PI constant
- M_1_PI constant
- M_E constant
- USE_MATH_DEFINES constant
- M_LOG2E constant
- M_LOG10E constant
- M_LN10 constant
- M_SQRT1_2 constant
- _USE_MATH_DEFINES constant
- M_PI_4 constant
- constants, math
- M_2_SQRTPI constant
- M_SQRT2 constant
- M_LN2 constant
ms.assetid: db533c3f-6ae8-4520-9d35-c8fabbef3529
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ca022fe2800a7c576af8d66e2e820be5f2375b5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="math-constants"></a>Matematik Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
#define _USE_MATH_DEFINES // for C++  
#include <cmath>  
  
#define _USE_MATH_DEFINES // for C  
#include <math.h>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki simgeler kendi belirtilen ifadeleri değerleri için tanımlanmıştır:  
  
|Simgesi|İfade|Değer|  
|------------|----------------|-----------|  
|M_E|e|2.71828182845904523536|  
|M_LOG2E|log2(e)|1.44269504088896340736|  
|M_LOG10E|log10(e)|0.434294481903251827651|  
|M_LN2|ln(2)|0.693147180559945309417|  
|M_LN10|ln(10)|2.30258509299404568402|  
|M_PI|pi|3.14159265358979323846|  
|M_PI_2|pi/2|1.57079632679489661923|  
|M_PI_4|pi/4|0.785398163397448309616|  
|M_1_PI|1/PI|0.318309886183790671538|  
|M_2_PI|2/PI|0.636619772367581343076|  
|M_2_SQRTPI|2/Sqrt(pi)|1.12837916709551257390|  
|M_SQRT2|Sqrt(2)|1.41421356237309504880|  
|M_SQRT1_2|1/Sqrt(2)|0.707106781186547524401|  
  
 Matematik sabitleri standart C/C++ içinde tanımlı değil. Bunları kullanmak için önce tanımlamanız gerekir `_USE_MATH_DEFINES` ve cmath veya math.h içerir.  
  
 Projenizi yayın modunda yapılandırıldığında ATLComTime.h dosya math.h içerir. Ayrıca ATLComTime.h içeren bir projede bir veya daha fazla matematik sabitleri kullanırsanız tanımlamanız gerekir `_USE_MATH_DEFINES` ATLComTime.h dahil etmeden önce.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Global Sabitler](../c-runtime-library/global-constants.md)