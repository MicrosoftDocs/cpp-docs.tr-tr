---
title: casin, casinf, casinl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- casin
- casinf
- casinl
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
- casin
- casinf
- casinl
- complex/casin
- complex/casinf
- complex/casinl
dev_langs: C++
helpviewer_keywords:
- casin function
- casinf function
- casinl function
ms.assetid: b75d1455-7b1e-43b0-bd46-c530be190be9
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5a059d34110e064a6e945d02bf83d39e6b5af637
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="casin-casinf-casinl"></a>casin, casinf, casinl
Dal keser gerçek ekseni boyunca [-1, + 1] aralığı dışında ile karmaşık bir sayının arksinüsünü alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_Dcomplex casin(   
   _Dcomplex z   
);  
_Fcomplex casin(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex casin(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex casinf(   
   _Fcomplex z   
);  
_Lcomplex casinl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `z`  
 Radyan cinsinden açı temsil eden bir karmaşık sayı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Arksinüsünü `z`, radyan cinsinden açı. Sonuç sanal ekseninde ve aralığında sınırsız [-π/2 + π/2] gerçek ekseni boyunca.  
  
## <a name="remarks"></a>Açıklamalar  
 Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz `casin` alın ve dönüş `_Fcomplex` ve `_Lcomplex` değerleri. Bir C programı `casin` her zaman alan ve döndüren bir `_Dcomplex` değeri.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|C üstbilgisi|C++ üstbilgi|  
|-------------|--------------|------------------|  
|`casin`,               `casinf`, `casinl`|\<Complex.h >|\<ccomplex >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [catanh, catanhf, catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [ctanh, ctanhf, ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [catan, catanf, catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [csinh, csinhf, csinhl](../../c-runtime-library/reference/csinh-csinhf-csinhl.md)   
 [casinh, casinhf, casinhl](../../c-runtime-library/reference/casinh-casinhf-casinhl.md)   
 [ccosh, ccoshf, ccoshl](../../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)   
 [cacosh, cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [cacos, cacosf, cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [ctan, ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [csin, csinf, csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [ccos, ccosf, ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [csqrt, csqrtf, csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)