---
title: fegetround, fesetround2 | Microsoft Docs
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
- fegetround
- fesetround
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fegetround
- fesetround
- fenv/fegetround
- fenv/fesetround
dev_langs: C++
helpviewer_keywords:
- fegetround function
- fesetround function
ms.assetid: 596af00b-be2f-4f57-b2f5-460485f9ff0b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 544a9e43f029ba03b2ccd40e7ab6fe4fdb1d8127
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fegetround-fesetround"></a>fegetround, fesetround
Alır veya ayarlar geçerli kayan nokta yuvarlama modu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int fegetround(void);  
  
int fesetround(  
   int round_mode  
);   
```  
  
#### <a name="parameters"></a>Parametreler  
 `round_mode`  
 , Kayan nokta yuvarlama makroları biri olarak ayarlamak için yuvarlama modu. Değeri kayan nokta yuvarlama makroları birine eşit değilse yuvarlama modu değiştirilmez.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı, `fegetround` yuvarlama modu makrosu değerleri yuvarlama kayan nokta döndürür. Geçerli yuvarlama modu belirlenemiyorsa negatif bir değer döndürür.  
  
 Başarılı, `fesetround` 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürülür.  
  
## <a name="remarks"></a>Açıklamalar  
 Kayan nokta işlemlerini birkaç yuvarlama modlarından birini kullanabilirsiniz. Bu sonuçları depolandığında kayan nokta işlemlerinin sonuçlarını doğru yuvarlanır hangi yönünü denetler. Bunlar adlarını ve kayan nokta yuvarlama makroları davranışlarını tanımlanan \<fenv.h >:  
  
|Makrosu|Açıklama|  
|-----------|-----------------|  
|FE_DOWNWARD|Negatif sonsuz doğru yuvarlar.|  
|FE_TONEAREST|Yuvarlak doğru en yakın.|  
|FE_TOWARDZERO|Sıfıra doğru yuvarlar.|  
|FE_UPWARD|Pozitif sonsuzluk doğru yuvarlar.|  
  
 Sonuçları yarıda doğru en yakın değere (0) bir daha az önemli bit ile gösterilebilir değerler arasında yuvarlanacak FE_TONEAREST varsayılan davranışını değil.  
  
 Geçerli yuvarlama modu işlemlerini etkiler:  
  
-   Dönüşümler dize.  
  
-   Kayan nokta aritmetik işleçler sabit ifadeler dışında sonuçları.  
  
-   İşlevler, gibi yuvarlama Kitaplığı `rint` ve `nearbyint`.  
  
-   Standart Kitaplığı matematik işlevleri dönüş değerleri.  
  
 Geçerli yuvarlama modu bu işlemleri etkilemez:  
  
-   `trunc`, `ceil`, `floor`, Ve `lround` kitaplık işlevleri.  
  
-   Tamsayı örtük atamalar ve her zaman sıfıra doğru yuvarlar dönüştürmeleri için kayan nokta.  
  
-   Kayan nokta aritmetik işleçler her zaman en yakın değere yuvarlar sabit ifadeler, sonuçları.  
  
 Bu işlevleri kullanmak için erişim kullanarak önleyebilir kayan nokta iyileştirmeler kapatmanız gerekir `#pragma fenv_access(on)` çağrı önce yönergesi. Daha fazla bilgi için bkz: [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`fegetround`,                `fesetround`|\<fenv.h >|\<cfenv >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [nearbyint, nearbyintf, nearbyintl](../../c-runtime-library/reference/nearbyint-nearbyintf-nearbyintl1.md)   
 [Yazdır, rintf, rintl](../../c-runtime-library/reference/rint-rintf-rintl.md)   
 [lrint, lrintf, lrintl, llrint, llrintf, llrintl](../../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)