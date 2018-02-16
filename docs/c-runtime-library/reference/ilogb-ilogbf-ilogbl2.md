---
title: ilogb, ilogbf, ilogbl2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- ilogb
- ilogbf
- ilogbl
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
- ilogb
- ilogbf
- ilogbl
- math/ilogb
- math/ilogbf
- math/ilogbl
helpviewer_keywords:
- ilogb function
- ilogbf function
- ilogbl function
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8da5ba71b59f64c38a051fd8f31fa7bf58a4556d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ilogb-ilogbf-ilogbl"></a>ilogb, ilogbf, ilogbl
Taraflı olmayan taban 2 üs. belirtilen değerin temsil eden bir tamsayı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int ilogb(  
   double x  
);  
  
int ilogb(  
   float x  
); //C++ only  
  
int ilogb(  
   long double x  
); //C++ only  
  
int ilogbf(  
   float x  
);  
  
int ilogbl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `x`  
 Belirtilen değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, temel 2 üs dönmek `x` işaretli olarak `int` değeri.  
  
 Aksi takdirde, tanımlanan aşağıdaki değerlerden birini döndürür \<math.h >:  
  
|Giriş|Sonuç|  
|-----------|------------|  
|±0|FP_ILOGB0|  
|±inf, ±nan belirsiz|FP_ILOGBNAN|  
  
 Hataları raporlanır belirtilmiş [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz `ilogb` alın ve float ve uzun çift türleri döndürür. Bir C programı `ilogb` her zaman alır ve bir double döndürür.  
  
 Bu işlev çağırma benzer eşdeğer çağırmak için `logb` işlevi sonra dönüş değerini atama `int`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|C üstbilgisi|C++ üstbilgi|  
|-------------|--------------|------------------|  
|`ilogb`,                `ilogbf`,  `ilogbl`|\<Math.h >|\<cmath >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [logb, logbf, logbl, _logb, _logbf](../../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)