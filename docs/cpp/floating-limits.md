---
title: Kayan Sınırları
ms.date: 08/03/2018
helpviewer_keywords:
- ranges, floating-point constants
- floating-point constants, limits
- float.h header file
- limits, floating-point constants
- floating-point numbers [C++]
- floating limits
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
ms.openlocfilehash: ccd395eef319e57cecffad8a5278b6df1397f4cb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373376"
---
# <a name="floating-limits"></a>Kayan Sınırları

**Microsoft'a Özgü**

Aşağıdaki tabloda kayan nokta sabitlerinin değerlerinin sınırları listelenistir. Bu sınırlar, standart üstbilgi dosyası \<float.h> de tanımlanır.

## <a name="limits-on-floating-point-constants"></a>Kayan Nokta Sabitleri Sınırlamaları

|Sabit|Anlamı|Değer|
|--------------|-------------|-----------|
|`FLT_DIG`<br/>`DBL_DIG`<br/>`LDBL_DIG`|Basamak sayısı, q, q ondalık basamaklı kayan nokta sayısı, bir kayan nokta gösterimi içine yuvarlanabilir ve hassaslık kaybı olmadan geri.|6<br/>15<br/>15|
|`FLT_EPSILON`<br/>`DBL_EPSILON`<br/>`LDBL_EPSILON`|En küçük pozitif sayı x, x + 1.0 1.0 eşit değildir gibi.|1.192092896e-07F<br/>2.2204460492503131e-016<br/>2.2204460492503131e-016|
|`FLT_GUARD`||0|
|`FLT_MANT_DIG`<br/>`DBL_MANT_DIG`<br/>`LDBL_MANT_DIG`|Radyatördeki basamak sayısı kayan nokta `FLT_RADIX` öneminde belirtilir. Radiks 2; bu nedenle bu değerler bitleri belirtir.|24<br/>53<br/>53|
|`FLT_MAX`<br/>`DBL_MAX`<br/>`LDBL_MAX`|Maksimum temsil edilebilir kayan nokta sayısı.|3.40282346e+38F<br/>1.7976931348623158e+308<br/>1.7976931348623158e+308|
|`FLT_MAX_10_EXP`<br/>`DBL_MAX_10_EXP`<br/>`LDBL_MAX_10_EXP`|Bu sayıya yükseltilmiş 10'u temsil eden kayan nokta sayısı gibi maksimum tamsayı.|38<br/>308<br/>308|
|`FLT_MAX_EXP`<br/>`DBL_MAX_EXP`<br/>`LDBL_MAX_EXP`|Bu sayıya yükseltilmiş `FLT_RADIX` maksimum tamsayı temsil edilebilir kayan nokta sayısıdır.|128<br/>1024<br/>1024|
|`FLT_MIN`<br/>`DBL_MIN`<br/>`LDBL_MIN`|En küçük pozitif değer.|1.175494351e-38F<br/>2.2250738585072014e-308<br/>2.2250738585072014e-308|
|`FLT_MIN_10_EXP`<br/>`DBL_MIN_10_EXP`<br/>`LDBL_MIN_10_EXP`|Bu sayıya yükseltilen 10'un temsil edilebilir kayan nokta sayısı olması gibi minimum negatif tamsayı.|-37<br/>-307<br/>-307|
|`FLT_MIN_EXP`<br/>`DBL_MIN_EXP`<br/>`LDBL_MIN_EXP`|Bu sayıya yükseltilen `FLT_RADIX` minimum negatif tamsayı temsil edilebilir kayan nokta sayısıdır.|-125<br/>-1021<br/>-1021|
|`FLT_NORMALIZE`||0|
|`FLT_RADIX`<br/>`_DBL_RADIX`<br/>`_LDBL_RADIX`|Üstel gösterimin sayı tabanı.|2<br/>2<br/>2|
|`FLT_ROUNDS`<br/>`_DBL_ROUNDS`<br/>`_LDBL_ROUNDS`|Kayan nokta ekleme için yuvarlama modu.|1 (yakın)<br/>1 (yakın)<br/>1 (yakın)|

> [!NOTE]
> Tablodaki bilgiler ürünün gelecekteki sürümlerinde farklılık gösterebilir.

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[Tamsayı Sınırları](../cpp/integer-limits.md)
