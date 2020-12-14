---
description: 'Daha fazla bilgi edinin: Floating-Point sabitleri için sınırlar'
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
ms.openlocfilehash: 345e57348843a62b99b1565b8966df682d5fed8c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257166"
---
# <a name="limits-on-floating-point-constants"></a>Kayan Nokta Sabitleri Sınırlamaları

**Microsoft'a Özgü**

Kayan noktalı sabitlerin değerlerine yönelik sınırlar aşağıdaki tabloda verilmiştir. Üstbilgi dosyası FLOAT.H bu bilgileri içerir.

### <a name="limits-on-floating-point-constants"></a>Kayan Nokta Sabitleri Sınırlamaları

|Sabit|Anlamı|Değer|
|--------------|-------------|-----------|
|**FLT_DIG**<br />**DBL_DIG**<br />**LDBL_DIG**|Bir kayan nokta gösterimine ve duyarlık kaybı olmadan bir kayan nokta temsiline yuvarlanabilir olması gibi, *s* *basamak sayısı* .|6<br />15<br />15|
|**FLT_EPSILON**<br />**DBL_EPSILON**<br />**LDBL_EPSILON**|*X* + 1,0, 1,0 değerine eşit olmayan en küçük pozitif sayı *x*|1.192092896 e-07F<br />2.2204460492503131 e-bir<br />2.2204460492503131 e-bir|
|**FLT_GUARD**||0|
|**FLT_MANT_DIG**<br />**DBL_MANT_DIG**<br />**LDBL_MANT_DIG**|Kayan nokta mantisinin içinde **FLT_RADIX** tarafından belirtilen taban 'teki basamak sayısı. Sayı tabanı 2'dir; bu nedenle bu değerler bitleri belirtir.|24<br />53<br />53|
|**FLT_MAX**<br />**DBL_MAX**<br />**LDBL_MAX**|Gösterilebilir en fazla kayan noktalı sayı.|3.402823466 e + 38F<br />1.7976931348623158 e + 308<br />1.7976931348623158 e + 308|
|**FLT_MAX_10_EXP**<br />**DBL_MAX_10_EXP**<br />**LDBL_MAX_10_EXP**|10 artırılınca gösterilebilir bir kayan noktalı sayı olan en yüksek tamsayı.|38<br />308<br />308|
|**FLT_MAX_EXP**<br />**DBL_MAX_EXP**<br />**LDBL_MAX_EXP**|Bu sayıya **FLT_RADIX** en büyük tamsayı, bir gösterilebilir tablo kayan noktalı sayıdır.|128<br />1024<br />1024|
|**FLT_MIN**<br />**DBL_MIN**<br />**LDBL_MIN**|En küçük pozitif değer.|1.175494351 e-38F<br />2.2250738585072014 e-308<br />2.2250738585072014 e-308|
|**FLT_MIN_10_EXP**<br />**DBL_MIN_10_EXP**<br />**LDBL_MIN_10_EXP**|10 artırılınca gösterilebilir bir kayan noktalı sayı olan en düşük negatif tamsayı.|-37<br />-307<br />-307|
|**FLT_MIN_EXP**<br />**DBL_MIN_EXP**<br />**LDBL_MIN_EXP**|En küçük negatif tamsayı, bu sayıya **FLT_RADIX** , bu sayının, gösterilebilir bir kayan noktalı sayıdır.|-125<br />-1021<br />-1021|
|**FLT_NORMALIZE**||0|
|**FLT_RADIX**<br />**_DBL_RADIX**<br />**_LDBL_RADIX**|Üstel gösterimin sayı tabanı.|2<br />2<br />2|
|**FLT_ROUNDS**<br />**_DBL_ROUNDS**<br />**_LDBL_ROUNDS**|Kayan nokta ekleme için yuvarlama modu.|1 (yakın)<br />1 (yakın)<br />1 (yakın)|

Yukarıdaki tabloda yer alan bilgilerin gelecekteki uygulamalarda değişebileceğini unutmayın.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Floating-Point sabitleri](../c-language/c-floating-point-constants.md)
