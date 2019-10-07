---
title: İmzasız tam sayı türlerinden dönüştürmeler
ms.date: 10/02/2019
helpviewer_keywords:
- integers, converting
- type casts, involving integers
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
- integral conversions, from unsigned
ms.assetid: 60fb7e10-bff9-4a13-8a48-e19f25a36a02
ms.openlocfilehash: 3099f0113103223e392dc20560899b4a6e3ebf20
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998794"
---
# <a name="conversions-from-unsigned-integral-types"></a>İmzasız tam sayı türlerinden dönüştürmeler

İşaretsiz bir tamsayı bir tamsayı veya kayan nokta türüne dönüştürüldüğünde, sonuç türünde orijinal değer gösterilebilir ise değer değiştirilmez.

İşaretsiz bir tamsayıyı daha büyük boyutlu bir tamsayıya dönüştürürken değer sıfır genişletilir. Daha küçük boyutta bir tamsayıya dönüştürürken, yüksek sıralı bitler kesilir. Sonuç, bu örnekte gösterildiği gibi sonuç türü kullanılarak yorumlanır.

```C
unsigned k = 65533;
short j;

j = k;
printf_s( "%hd\n", j );   // Prints -3
```

İşaretsiz bir tamsayı bir kayan nokta türüne dönüştürülürken, özgün değer tam olarak sonuç türünde temsil edilene kadar, sonuç bir sonraki daha yüksek veya daha düşük gösterilemeyen değerdir.

İntegral ve kayan nokta türlerinin boyutları hakkında bilgi için bkz. [temel türlerin depolanması](../c-language/storage-of-basic-types.md) .

**Microsoft 'a özgü**

Microsoft derleyicisinde, **imzasız** (veya **işaretsiz int**) ve **işaretsiz Long** farklıdır ancak eşdeğer türlerdir. **İşaretsiz bir int** değerin dönüştürülmesi, **işaretsiz bir Long**değeri dönüştürülürken aynı şekilde devam eder.

**SON Microsoft 'a özgü**

Aşağıdaki tabloda, imzasız integral türlerinden dönüşümler özetlenmektedir.

## <a name="table-of-conversions-from-unsigned-integral-types"></a>İşaretsiz integral türlerindeki dönüştürmelerin tablosu

|Başlangıç|Bitiş|Yöntem|
|----------|--------|------------|
|**işaretsiz karakter**|**char**|Bit modelini koru; yüksek sıralı bit, işaret biti olur|
|**işaretsiz karakter**|**short**|Sıfır-uzat|
|**işaretsiz karakter**|**long**|Sıfır-uzat|
|**işaretsiz karakter**|**uzun uzun**|Sıfır-uzat|
|**işaretsiz karakter**|**işaretsiz kısa**|Sıfır-uzat|
|**işaretsiz karakter**|**imzasız Long**|Sıfır-uzat|
|**işaretsiz karakter**|**imzasız uzun uzun**|Sıfır-uzat|
|**işaretsiz karakter**|**float**|**Long**'a Dönüştür; **uzun** **kaya** Dönüştür|
|**işaretsiz karakter**|**double**|**Long**'a Dönüştür; **uzun** - **çift** Dönüştür|
|**işaretsiz karakter**|**uzun çift**|**Long**'a Dönüştür; **uzun** - **çift** Dönüştür|
|**işaretsiz kısa**|**char**|Düşük sıra baytını koru|
|**işaretsiz kısa**|**short**|Bit modelini koru; yüksek sıralı bit, işaret biti olur|
|**işaretsiz kısa**|**long**|Sıfır-uzat|
|**işaretsiz kısa**|**uzun uzun**|Sıfır-uzat|
|**işaretsiz kısa**|**işaretsiz karakter**|Düşük sıra baytını koru|
|**işaretsiz kısa**|**imzasız Long**|Sıfır-uzat|
|**işaretsiz kısa**|**imzasız uzun uzun**|Sıfır-uzat|
|**işaretsiz kısa**|**float**|**Long**'a Dönüştür; **uzun** **kaya** Dönüştür|
|**işaretsiz kısa**|**double**|**Long**'a Dönüştür; **uzun** - **çift** Dönüştür|
|**işaretsiz kısa**|**uzun çift**|**Long**'a Dönüştür; **uzun** - **çift** Dönüştür|
|**imzasız Long**|**char**|Düşük sıra baytını koru|
|**imzasız Long**|**short**|Düşük sıralı kelimeyi koru|
|**imzasız Long**|**long**|Bit modelini koru; yüksek sıralı bit, işaret biti olur|
|**imzasız Long**|**uzun uzun**|Sıfır-uzat|
|**imzasız Long**|**işaretsiz karakter**|Düşük sıra baytını koru|
|**imzasız Long**|**işaretsiz kısa**|Düşük sıralı kelimeyi koru|
|**imzasız Long**|**imzasız uzun uzun**|Sıfır-uzat|
|**imzasız Long**|**float**|**Long**'a Dönüştür; **uzun** **kaya** Dönüştür|
|**imzasız Long**|**double**|Doğrudan **Double** 'a Dönüştür|
|**imzasız Long**|**uzun çift**|**Long**'a Dönüştür; **uzun** - **çift** Dönüştür|
|**imzasız uzun uzun**|**char**|Düşük sıra baytını koru|
|**imzasız uzun uzun**|**short**|Düşük sıralı kelimeyi koru|
|**imzasız uzun uzun**|**long**|Düşük sıralı DWORD 'yi koru|
|**imzasız uzun uzun**|**uzun uzun**|Bit modelini koru; yüksek sıralı bit, işaret biti olur|
|**imzasız uzun uzun**|**işaretsiz karakter**|Düşük sıra baytını koru|
|**imzasız uzun uzun**|**işaretsiz kısa**|Düşük sıralı kelimeyi koru|
|**imzasız uzun uzun**|**imzasız Long**|Düşük sıralı DWORD 'yi koru|
|**imzasız uzun uzun**|**float**|**Long**'a Dönüştür; **uzun** **kaya** Dönüştür|
|**imzasız uzun uzun**|**double**|Doğrudan **Double** 'a Dönüştür|
|**imzasız uzun uzun**|**uzun çift**|**Long**'a Dönüştür; **uzun** - **çift** Dönüştür|

## <a name="see-also"></a>Ayrıca bkz.

[Atama dönüştürmeleri](../c-language/assignment-conversions.md)
