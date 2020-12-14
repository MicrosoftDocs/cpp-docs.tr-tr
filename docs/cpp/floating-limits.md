---
description: Daha fazla bilgi için bkz. kayan sınırlar
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
ms.openlocfilehash: 92694ee605d7cec12d03d808168b095f5c9f447b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242593"
---
# <a name="floating-limits"></a>Kayan Sınırları

**Microsoft'a Özgü**

Aşağıdaki tabloda kayan nokta sabitlerinin değerlerine ilişkin sınırlar listelenmektedir. Bu sınırlar ayrıca standart üstbilgi dosyasında da tanımlanmıştır \<float.h> .

## <a name="limits-on-floating-point-constants"></a>Kayan Nokta Sabitleri Sınırlamaları

|Sabit|Anlamı|Değer|
|--------------|-------------|-----------|
|`FLT_DIG`<br/>`DBL_DIG`<br/>`LDBL_DIG`|Bir kayan nokta gösterimine ve duyarlık kaybı olmadan bir kayan nokta temsiline yuvarlanabilir olması gibi, s basamak sayısı.|6<br/>15<br/>15|
|`FLT_EPSILON`<br/>`DBL_EPSILON`<br/>`LDBL_EPSILON`|X + 1,0 gibi en küçük pozitif sayı, 1,0 değerine eşit değildir.|1.192092896 e-07F<br/>2.2204460492503131 e-bir<br/>2.2204460492503131 e-bir|
|`FLT_GUARD`||0|
|`FLT_MANT_DIG`<br/>`DBL_MANT_DIG`<br/>`LDBL_MANT_DIG`|Kayan nokta mantisinin tarafından belirtilen taban içindeki basamak sayısı `FLT_RADIX` . Taban 2 ' dir; Bu nedenle bu değerler bitleri belirtir.|24<br/>53<br/>53|
|`FLT_MAX`<br/>`DBL_MAX`<br/>`LDBL_MAX`|En yüksek gösterilebilir tablo kayan noktalı sayı.|3.402823466 e + 38F<br/>1.7976931348623158 e + 308<br/>1.7976931348623158 e + 308|
|`FLT_MAX_10_EXP`<br/>`DBL_MAX_10_EXP`<br/>`LDBL_MAX_10_EXP`|10 ' un bu sayıya kadar harekete geçirilen en büyük tamsayı, gösterilebilir bir kayan noktalı sayıdır.|38<br/>308<br/>308|
|`FLT_MAX_EXP`<br/>`DBL_MAX_EXP`<br/>`LDBL_MAX_EXP`|Bu sayıyla oluşturulan en büyük tamsayı `FLT_RADIX` , gösterilebilir bir kayan noktalı sayıdır.|128<br/>1024<br/>1024|
|`FLT_MIN`<br/>`DBL_MIN`<br/>`LDBL_MIN`|En küçük pozitif değer.|1.175494351 e-38F<br/>2.2250738585072014 e-308<br/>2.2250738585072014 e-308|
|`FLT_MIN_10_EXP`<br/>`DBL_MIN_10_EXP`<br/>`LDBL_MIN_10_EXP`|10 ' un bu sayıya kadar harekete geçirilen en küçük negatif tamsayı, gösterilebilir bir kayan noktalı sayıdır.|-37<br/>-307<br/>-307|
|`FLT_MIN_EXP`<br/>`DBL_MIN_EXP`<br/>`LDBL_MIN_EXP`|Bu sayıyla oluşturulan en küçük negatif tamsayı `FLT_RADIX` , gösterilebilir bir kayan noktalı sayıdır.|-125<br/>-1021<br/>-1021|
|`FLT_NORMALIZE`||0|
|`FLT_RADIX`<br/>`_DBL_RADIX`<br/>`_LDBL_RADIX`|Üstel gösterimin sayı tabanı.|2<br/>2<br/>2|
|`FLT_ROUNDS`<br/>`_DBL_ROUNDS`<br/>`_LDBL_ROUNDS`|Kayan nokta ekleme için yuvarlama modu.|1 (yakın)<br/>1 (yakın)<br/>1 (yakın)|

> [!NOTE]
> Tablodaki bilgiler ürünün gelecekteki sürümlerinde farklılık gösterebilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Tamsayı sınırları](../cpp/integer-limits.md)
