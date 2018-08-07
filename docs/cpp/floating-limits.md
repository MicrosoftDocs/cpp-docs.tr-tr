---
title: Kayan sınırları | Microsoft Docs
ms.custom: ''
ms.date: 08/03/2018
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
ms.openlocfilehash: 85a31aea113514651fc3e81ac147b5ea2974920c
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604300"
---
# <a name="floating-limits"></a>Kayan Sınırları

**Microsoft'a özgü**

Aşağıdaki tabloda, kayan nokta sabitleri değerlerini sınırlar listelenmektedir. Bu sınırlar da standart üstbilgi dosyasında tanımlanan \<float.h >.  

## <a name="limits-on-floating-point-constants"></a>Kayan Nokta Sabitleri Sınırlamaları

|Sabit|Açıklama|Değer|
|--------------|-------------|-----------|
|`FLT_DIG`<br/>`DBL_DIG`<br/>`LDBL_DIG`|Basamak sayısı q, böyle bir kayan noktalı sayı q ondalık basamakları olan bir kayan nokta gösterimi ve duyarlık kaybı olmadan geri olarak yuvarlanmasını.|6<br/>15<br/>15|
|`FLT_EPSILON`<br/>`DBL_EPSILON`<br/>`LDBL_EPSILON`|En küçük pozitif sayıyı x, örneğin, x + 1.0 1.0 eşit değil.|1.192092896e-07F<br/>2.2204460492503131e-016<br/>2.2204460492503131e-016|
|`FLT_GUARD`||0|
|`FLT_MANT_DIG`<br/>`DBL_MANT_DIG`<br/>`LDBL_MANT_DIG`|Tarafından belirtilen sayı basamak sayısını `FLT_RADIX` kayan nokta anlam olarak. Sayı tabanı 2'dir; Bu nedenle bu değerler bitleri belirtir.|24<br/>53<br/>53|
|`FLT_MAX`<br/>`DBL_MAX`<br/>`LDBL_MAX`|Gösterilebilir en fazla kayan noktalı sayı.|3.402823466e + 38F<br/>1.7976931348623158e + 308<br/>1.7976931348623158e + 308|
|`FLT_MAX_10_EXP`<br/>`DBL_MAX_10_EXP`<br/>`LDBL_MAX_10_EXP`|Bu sayıya 10 yükseltilmiş şekilde en büyük tamsayı gösterilebilir bir kayan noktalı sayı olan.|38<br/>308<br/>308|
|`FLT_MAX_EXP`<br/>`DBL_MAX_EXP`<br/>`LDBL_MAX_EXP`|En büyük tamsayı şekilde `FLT_RADIX` gösterilebilir bir kayan nokta sayı sayıdır oluşturulur.|128<br/>1024<br/>1024|
|`FLT_MIN`<br/>`DBL_MIN`<br/>`LDBL_MIN`|En küçük pozitif değer.|1.175494351e-38F<br/>2.2250738585072014e-308<br/>2.2250738585072014e-308|
|`FLT_MIN_10_EXP`<br/>`DBL_MIN_10_EXP`<br/>`LDBL_MIN_10_EXP`|Bu sayıya 10 gerçekleşti, en düşük negatif tamsayı gösterilebilir bir kayan nokta sayı ' dir.|-37<br/>-307<br/>-307|
|`FLT_MIN_EXP`<br/>`DBL_MIN_EXP`<br/>`LDBL_MIN_EXP`|En düşük negatif tamsayı şekilde `FLT_RADIX` gösterilebilir bir kayan noktalı sayı sayıdır oluşturulur.|-125<br/>-1021<br/>-1021|
|`FLT_NORMALIZE`||0|
|`FLT_RADIX`<br/>`_DBL_RADIX`<br/>`_LDBL_RADIX`|Üstel gösterimin sayı tabanı.|2<br/>2<br/>2|
|`FLT_ROUNDS`<br/>`_DBL_ROUNDS`<br/>`_LDBL_ROUNDS`|Kayan nokta ekleme için yuvarlama modu.|1 (yakın)<br/>1 (yakın)<br/>1 (yakın)|

> [!NOTE]
>  Tabloda yer alan bilgiler, ileride ürün sürümleri farklı olabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Tamsayı Sınırları](../cpp/integer-limits.md)  
