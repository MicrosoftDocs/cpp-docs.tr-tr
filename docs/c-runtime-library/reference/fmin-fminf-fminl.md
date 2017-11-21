---
title: fmin, fminf, fminl | Microsoft Docs
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
- fmin
- fminf
- fminl
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
- fmin
- fminf
- fminl
- math/fmin
- math/fminf
- math/fminl
helpviewer_keywords:
- fmin function
- fminf function
- fminl function
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4e8fd804c63caa1a8558e19cb67b4b3f35ecf180
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fmin-fminf-fminl"></a>fmin, fminf, fminl
Belirtilen iki değerin daha küçük belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double fmin(  
   double x,   
   double y  
);  
  
float fmin(  
   float x,   
   float y  
); //C++ only  
  
long double fmin(  
   long double x,   
   long double y  
); //C++ only  
  
float fminf(  
   float x,   
   float y  
);  
  
long double fminl(  
   long double x,   
   long double y  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `x`  
 Karşılaştırılacak ilk değer.  
  
 `y`  
 Karşılaştırılacak ikinci değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür küçük olanını `x` veya `y`.  
  
|Giriş|Sonuç|  
|-----------|------------|  
|`x`NaN olup|`y`|  
|`y`NaN olup|`x`|  
|`x`ve `y` NaN olan|NaN|  
  
 İşlev neden olmaz [_matherr](../../c-runtime-library/reference/matherr.md) çağrılacak, kayan nokta özel durumlar neden veya değerini değiştirmek `errno`.  
  
## <a name="remarks"></a>Açıklamalar  
 Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz `fmin` alın ve float ve uzun çift türleri döndürür. Bir C programı `fmin` her zaman alır ve bir double döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`fmin`, `fminf`, `fminl`|C: \<math.h ><br />C++: \<math.h > veya \<cmath >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)  
 [fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)  