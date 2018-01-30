---
title: expm1, expm1f, expm1l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- expm1l
- expm1
- expm1f
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
- expm1l
- expm1
- expm1f
dev_langs:
- C++
helpviewer_keywords:
- expm1f function
- expm1l function
- expm1 function
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e02b2b481e1b773e780623d43ae94d8abe0cba2
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="expm1-expm1f-expm1l"></a>expm1, expm1f, expm1l
E tabanında bir eksi bir değer üstel hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double expm1(   
   double x   
);  
float expm1(  
   float x  
);  // C++ only  
long double expm1(  
   long double x  
);  // C++ only  
float expm1f(  
   float x  
);  
long double expm1l(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `x`  
 Kayan nokta üstel değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `expm1` İşlevleri dönüş e temsil eden bir kayan nokta değeri<sup>x</sup> - 1, başarılı olursa. Taşma, `expm1` döndürür `HUGE_VAL`, `expm1f` döndürür `HUGE_VALF`, `expm1l` döndürür `HUGE_VALL`, ve `errno` ayarlanır `ERANGE`. Dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz `expm1` alın ve dönüş `float` ve `long double` değerleri. Bir C programı `expm1` her zaman alan ve döndüren bir `double`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`expm1`, `expm1f`, `expm1l`|\<Math.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)   
 [pow, powf, powl](../../c-runtime-library/reference/pow-powf-powl.md)