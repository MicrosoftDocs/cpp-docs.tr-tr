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
ms.openlocfilehash: 9a111d2ea3e8e5503754b0d9c0c1a4f69170a41c
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401765"
---
# <a name="floating-limits"></a>Kayan Sınırları
**Microsoft'a özgü**  
  
 Aşağıdaki tabloda, kayan nokta sabitleri değerlerini sınırlar listelenmektedir. Bu sınırlar da standart üstbilgi dosyasında tanımlanan \<float.h >.  
  
### <a name="limits-on-floating-point-constants"></a>Kayan Nokta Sabitleri Sınırlamaları  
  
|Sabit|Açıklama|Değer|  
|--------------|-------------|-----------|  
|FLT_DIG DBL_DIG LDBL_DIG|Basamak sayısı q, böyle bir kayan noktalı sayı q ondalık basamakları olan bir kayan nokta gösterimi ve duyarlık kaybı olmadan geri olarak yuvarlanmasını.|6 15 15|  
|FLT_EPSILON DBL_EPSILON LDBL_EPSILON|En küçük pozitif sayıyı x, örneğin, x + 1.0 1.0 eşit değil.|1.192092896e-07F 2.2204460492503131e-016 2.2204460492503131e-016|  
|FLT_GUARD||0|  
|FLT_MANT_DIG DBL_MANT_DIG LDBL_MANT_DIG|Kayan nokta anlam flt_radıx tarafından belirtilen sayı basamak sayısı. Sayı tabanı 2'dir; Bu nedenle bu değerler bitleri belirtir.|24 53 53|  
|FLT_MAX DBL_MAX LDBL_MAX|Gösterilebilir en fazla kayan noktalı sayı.|3.402823466e+38F 1.7976931348623158e+308 1.7976931348623158e+308|  
|FLT_MAX_10_EXP DBL_MAX_10_EXP LDBL_MAX_10_EXP|Bu sayıya 10 yükseltilmiş şekilde en büyük tamsayı gösterilebilir bir kayan noktalı sayı olan.|38 308 308|  
|FLT_MAX_EXP DBL_MAX_EXP LDBL_MAX_EXP|Bu sayıya flt_radıx gerçekleşti, en büyük tamsayı gösterilebilir bir kayan nokta sayı ' dir.|128 1024 1024|  
|FLT_MIN DBL_MIN LDBL_MIN|En küçük pozitif değer.|1.175494351e-38F 2.2250738585072014e-308 2.2250738585072014e-308|  
|FLT_MIN_10_EXP DBL_MIN_10_EXP LDBL_MIN_10_EXP|Bu sayıya 10 gerçekleşti, en düşük negatif tamsayı gösterilebilir bir kayan nokta sayı ' dir.|-37<br /><br /> -307<br /><br /> -307|  
|FLT_MIN_EXP DBL_MIN_EXP LDBL_MIN_EXP|Bu sayıya flt_radıx gerçekleşti, en düşük negatif tamsayı gösterilebilir bir kayan noktalı sayı olan.|-125<br /><br /> -1021<br /><br /> -1021|  
|FLT_NORMALIZE||0|  
|FLT_RADIX _DBL_RADIX _LDBL_RADIX|Üstel gösterimin sayı tabanı.|2 2 2|  
|FLT_ROUNDS _DBL_ROUNDS _LDBL_ROUNDS|Kayan nokta ekleme için yuvarlama modu.|1 (yakın) 1 (yakın) 1 (yakın)|  
  
> [!NOTE]
>  Tabloda yer alan bilgiler, ileride ürün sürümleri farklı olabilir.  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Tamsayı Sınırları](../cpp/integer-limits.md)