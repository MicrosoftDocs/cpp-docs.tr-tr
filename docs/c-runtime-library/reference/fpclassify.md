---
title: fpclassify | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apiname: fpclassify
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
apitype: HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e38ca3275c290d96fd5cf7910044abc32721eb85
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fpclassify"></a>fpclassify
Kayan nokta sınıflandırmasını bağımsız değişkeni döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int fpclassify(   
   /* floating-point */ x   
);  
  
int fpclassify(   
   float x   
); // C++ only  
  
int fpclassify(   
   double x   
); // C++ only  
  
int fpclassify(   
   long double x   
); // C++ only  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `x`  
 Test etmek için kayan nokta değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `fpclassify`kayan nokta sınıfı bağımsız değişkenin gösteren bir Integer değeri döndürür `x`. Bu tablo tarafından döndürülen olası değerleri gösterir `fpclassify`, içinde tanımlı \<math.h >.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`FP_NAN`|Bir sessiz, sinyal veya belirsiz NaN|  
|`FP_INFINITE`|Pozitif veya negatif sonsuzluk|  
|`FP_NORMAL`|Olumlu veya olumsuz normalleştirilmiş sıfır değeri|  
|`FP_SUBNORMAL`|Pozitif veya negatif bir Normalleştirilmemiş değeri|  
|`FP_ZERO`|Bir pozitif veya sıfır değeri negatif|  
  
## <a name="remarks"></a>Açıklamalar  
 C, `fpclassify` makro; C++ ' ta `fpclassify` bağımsız değişken türleri kullanarak aşırı işlevi `float`, `double`, veya `long double`. Her iki durumda da, döndürülen değer bağımsız değişken ifadesi etkili türü ve değil tüm ara gösterimi bağlıdır. Örneğin, normal `double` veya `long double` değeri bir sonsuzluk duruma, normal dışı veya sıfır için dönüştürüldüğünde değeri bir `float`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev/makrosu|Gerekli üstbilgisi (C)|Gerekli üstbilgisi (C++)|  
|---------------------|---------------------------|-------------------------------|  
|`fpclassify`|\<Math.h >|\<Math.h > veya \<cmath >|  
  
 `fpclassify` Makrosu ve `fpclassify` işlevleri uygun C99 ve C ++ 11 belirtimleri. Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [isNaN, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)