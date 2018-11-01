---
title: Kayan Nokta Sabitleri Sınırlamaları
ms.date: 11/04/2016
helpviewer_keywords:
- ranges, floating-point constants
- floating-point constants, limits
- FLOAT.H header file
- constants, floating-point
- limits, floating-point constants
- floating-point numbers, floating limits
ms.assetid: 2d975868-2af6-45d7-a8af-db79f2c6b67b
ms.openlocfilehash: 545c8fc356d7e1a6c56fdd5c144fa9a55120c97f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50664119"
---
# <a name="limits-on-floating-point-constants"></a>Kayan Nokta Sabitleri Sınırlamaları

**Microsoft'a özgü**

Kayan noktalı sabitlerin değerlerine yönelik sınırlar aşağıdaki tabloda verilmiştir. Üstbilgi dosyası FLOAT.H bu bilgileri içerir.

### <a name="limits-on-floating-point-constants"></a>Kayan Nokta Sabitleri Sınırlamaları

|Sabit|Açıklama|Değer|
|--------------|-------------|-----------|
|**FLT_DIG**<br />**DBL_DIG**<br />**LDBL_DIG**|Basamak sayısı *q*gibi bir kayan noktalı sayı ile *q* ondalık basamak yuvarlak bir kayan nokta gösterimi ve duyarlık kaybı olmadan geri.|6<br />15<br />15|
|**FLT_EPSILON**<br />**DBL_EPSILON**<br />**LDBL_EPSILON**|En küçük pozitif sayıyı *x*gibi *x* + 1.0, 1.0 eşit değil|1.192092896e-07F<br />2.2204460492503131e-016<br />2.2204460492503131e-016|
|**FLT_GUARD**||0|
|**FLT_MANT_DIG**<br />**DBL_MANT_DIG**<br />**LDBL_MANT_DIG**|Tarafından belirtilen sayı basamak sayısını **flt_radıx** kayan nokta anlam olarak. Sayı tabanı 2'dir; bu nedenle bu değerler bitleri belirtir.|24<br />53<br />53|
|**FLT_MAX**<br />**DBL_MAX**<br />**LDBL_MAX**|Gösterilebilir en fazla kayan noktalı sayı.|3.402823466e + 38F<br />1.7976931348623158e + 308<br />1.7976931348623158e + 308|
|**FLT_MAX_10_EXP**<br />**DBL_MAX_10_EXP**<br />**LDBL_MAX_10_EXP**|10 artırılınca gösterilebilir bir kayan noktalı sayı olan en yüksek tamsayı.|38<br />308<br />308|
|**FLT_MAX_EXP**<br />**DBL_MAX_EXP**<br />**LDBL_MAX_EXP**|En büyük tamsayı şekilde **flt_radıx** gösterilebilir bir kayan noktalı sayı sayıdır oluşturulur.|128<br />1024<br />1024|
|**FLT_MIN**<br />**DBL_MIN**<br />**LDBL_MIN**|En küçük pozitif değer.|1.175494351e-38F<br />2.2250738585072014e-308<br />2.2250738585072014e-308|
|**FLT_MIN_10_EXP**<br />**DBL_MIN_10_EXP**<br />**LDBL_MIN_10_EXP**|10 artırılınca gösterilebilir bir kayan noktalı sayı olan en düşük negatif tamsayı.|-37<br />-307<br />-307|
|**FLT_MIN_EXP**<br />**DBL_MIN_EXP**<br />**LDBL_MIN_EXP**|En düşük negatif tamsayı şekilde **flt_radıx** gösterilebilir bir kayan noktalı sayı sayıdır oluşturulur.|-125<br />-1021<br />-1021|
|**FLT_NORMALIZE**||0|
|**FLT_RADIX**<br />**_DBL_RADIX**<br />**_LDBL_RADIX**|Üstel gösterimin sayı tabanı.|2<br />2<br />2|
|**FLT_ROUNDS**<br />**_DBL_ROUNDS**<br />**_LDBL_ROUNDS**|Kayan nokta ekleme için yuvarlama modu.|1 (yakın)<br />1 (yakın)<br />1 (yakın)|

Yukarıdaki tabloda yer alan bilgilerin gelecekteki uygulamalarda değişebileceğini unutmayın.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[C Kayan Nokta Sabitleri](../c-language/c-floating-point-constants.md)