---
title: Kayan sınırları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ranges, floating-point constants
- floating-point constants, limits
- float.h header file
- limits, floating-point constants
- floating-point numbers [C++]
- floating limits
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7bba2bef20cbe5820d2a7feaae5743f151aea9da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417474"
---
# <a name="floating-limits"></a>Kayan Sınırları
**Microsoft özel**  
  
 Aşağıdaki tabloda değerlerini kayan nokta sabitleri sınırlamaları listeler. Bu sınırlar da standart üstbilgi dosyasında tanımlanan \<float.h >.  
  
### <a name="limits-on-floating-point-constants"></a>Kayan Nokta Sabitleri Sınırlamaları  
  
|Sabit|Açıklama|Değer|  
|--------------|-------------|-----------|  
|FLT_DIG DBL_DIG LDBL_DIG|Basamak sayısı q, böyle bir kayan noktalı sayının q ondalık basamak içeren bir kayan nokta temsili içine ve duyarlık kaybı olmadan geri olarak yuvarlanmasını.|6 15 15|  
|FLT_EPSILON DBL_EPSILON LDBL_EPSILON|En küçük pozitif sayıyı x, örneğin, x + 1.0 1.0 eşit değil.|1.192092896e-07F 2.2204460492503131e-016 2.2204460492503131e-016|  
|FLT_GUARD||0|  
|FLT_MANT_DIG DBL_MANT_DIG LDBL_MANT_DIG|Kayan nokta significand içinde flt_radıx tarafından belirtilen sayı tabanını basamak sayısı. Sayı tabanını 2'dir; Bu nedenle bu değerleri BITS belirtin.|24 53 53|  
|FLT_MAX DBL_MAX LDBL_MAX|Gösterilebilir kayan nokta sayısı.|3.402823466e+38F 1.7976931348623158e+308 1.7976931348623158e+308|  
|FLT_MAX_10_EXP DBL_MAX_10_EXP LDBL_MAX_10_EXP|Bu sayıya 10 yükseltilmiş şekilde maksimum gösterilebilir kayan noktalı sayı tamsayıdır.|38 308 308|  
|FLT_MAX_EXP DBL_MAX_EXP LDBL_MAX_EXP|Bu sayıya flt_radıx gerçekleşti, en fazla gösterilebilir bir kayan noktalı sayı tamsayıdır.|128 1024 1024|  
|FLT_MIN DBL_MIN LDBL_MIN|En küçük pozitif değer.|1.175494351e-38F 2.2250738585072014e-308 2.2250738585072014e-308|  
|FLT_MIN_10_EXP DBL_MIN_10_EXP LDBL_MIN_10_EXP|Bu sayıya 10 yükseltilmiş şekilde en az negatif gösterilebilir bir kayan noktalı sayı tamsayıdır.|-37<br /><br /> -307<br /><br /> -307|  
|FLT_MIN_EXP DBL_MIN_EXP LDBL_MIN_EXP|Bu sayıya flt_radıx gerçekleşti, en az negatif gösterilebilir kayan noktalı sayı tamsayıdır.|-125<br /><br /> -1021<br /><br /> -1021|  
|FLT_NORMALIZE||0|  
|FLT_RADIX _DBL_RADIX _LDBL_RADIX|Üstel gösterimin sayı tabanı.|2 2 2|  
|FLT_ROUNDS _DBL_ROUNDS _LDBL_ROUNDS|Kayan nokta eklenmesi için yuvarlama modu.|1 (yakın) 1 (yakın) 1 (yakın)|  
  
> [!NOTE]
>  Tabloda yer alan bilgiler, ileride ürün sürümleri farklı olabilir.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tamsayı Sınırları](../cpp/integer-limits.md)