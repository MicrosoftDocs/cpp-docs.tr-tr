---
title: İmzalı tam sayı türlerinden dönüştürmeler
ms.date: 10/02/2019
helpviewer_keywords:
- integral conversions, from signed
- integers, converting
- conversions [C++], integral
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
ms.assetid: 5eea32f8-8b14-413d-acac-c063b3d118d7
ms.openlocfilehash: 79608b5ca4335ee3c30bdab27e7efade5b7e2f54
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998727"
---
# <a name="conversions-from-signed-integral-types"></a>İmzalı tam sayı türlerinden dönüştürmeler

İşaretli bir tamsayı bir tamsayıya veya kayan nokta türüne dönüştürüldüğünde, özgün değer sonuç türünde gösterilebilir ise, değer değiştirilmez.

İşaretli bir tamsayı daha büyük bir tamsayıya dönüştürüldüğünde, değer, işaret genişletilir. Daha küçük boyutlu bir tamsayıya dönüştürüldüğünde, yüksek sıralı bitler kesilir. Sonuç, bu örnekte gösterildiği gibi sonuç türü kullanılarak yorumlanır:

```C
int i = -3;
unsigned short u;

u = i;
printf_s( "%hu\n", u );  // Prints 65533
```

İşaretli bir tamsayı bir kayan nokta türüne dönüştürülürken, özgün değer tam olarak sonuç türünde gösterilemeyen şekilde yoksa, sonuç bir sonraki daha yüksek veya daha düşük gösterilemeyen değerdir.

İntegral ve kayan nokta türlerinin boyutları hakkında daha fazla bilgi için bkz. [temel türlerin depolanması](../c-language/storage-of-basic-types.md).

Aşağıdaki tabloda, imzalanmış integral türlerinden dönüşümler özetlenmektedir. Bu, **char** türünün varsayılan olarak imzalandığını varsayar. **Karakter** türü için varsayılan ayarı işaretsiz olarak değiştirmek için bir derleme zamanı seçeneği kullanırsanız, **imzasız karakter** türü için [imzasız integral türler tablosundan dönüştürmelerde](../c-language/conversions-from-unsigned-integral-types.md) verilen dönüştürmeler, bu tablodaki dönüştürmeler yerine geçerlidir.

**Microsoft 'a özgü**

Microsoft derleyicisi, **int** ve **Long** birbirinden farklıdır ancak eşdeğer türlerdir. Bir **int** değerin dönüştürülmesi, **uzun**dönüştürme ile aynı şekilde devam eder.

**SON Microsoft 'a özgü**

## <a name="table-of-conversions-from-signed-integral-types"></a>İşaretli integral türlerinden dönüştürme tablosu

|Başlangıç|Bitiş|Yöntem|
|----------|--------|------------|
|**karakter**<sup>1</sup>|**short**|Oturum uzat|
|**char**|**long**|Oturum uzat|
|**char**|**uzun uzun**|Oturum uzat|
|**char**|**işaretsiz karakter**|Stili koru; yüksek sıralı bit, işaret biti olarak işlevi kaybeder|
|**char**|**işaretsiz kısa**|İmza- **kısa**olarak genişletilir; **Short** 'ı **işaretsiz Short** 'a Dönüştür|
|**char**|**imzasız Long**|İmza- **uzun**olarak genişletilir; **uzun** ve **işaretsiz uzunlukta** Dönüştür|
|**char**|**imzasız uzun uzun**|İmza- **uzun uzun**, uzatma **uzun** uzun veya **işaretsiz** Long Long 'ı Dönüştür|
|**char**|**float**|İmza- **uzun**olarak genişletilir; **uzun** **kaya** Dönüştür|
|**char**|**double**|İmza- **uzun**olarak genişletilir; **uzun** - **çift** Dönüştür|
|**char**|**uzun çift**|İmza- **uzun**olarak genişletilir; **uzun** - **çift** Dönüştür|
|**short**|**char**|Düşük sıra baytını koru|
|**short**|**long**|Oturum uzat|
|**short**|**uzun uzun**|Oturum uzat|
|**short**|**işaretsiz karakter**|Düşük sıra baytını koru|
|**short**|**işaretsiz kısa**|Bit modelini koru; yüksek sıralı bit, işaret biti olarak işlevi kaybeder|
|**short**|**imzasız Long**|İmza- **uzun**olarak genişletilir; **uzun** ve **işaretsiz uzunlukta** Dönüştür|
|**short**|**imzasız uzun uzun**|İmza- **uzun uzun**, uzatma **uzun** uzun veya **işaretsiz** Long Long 'ı Dönüştür|
|**short**|**float**|İmza- **uzun**olarak genişletilir; **uzun** **kaya** Dönüştür|
|**short**|**double**|İmza- **uzun**olarak genişletilir; **uzun** - **çift** Dönüştür|
|**short**|**uzun çift**|İmza- **uzun**olarak genişletilir; **uzun** - **çift** Dönüştür|
|**long**|**char**|Düşük sıra baytını koru|
|**long**|**short**|Düşük sıralı kelimeyi koru|
|**long**|**uzun uzun**|Oturum uzat|
|**long**|**işaretsiz karakter**|Düşük sıra baytını koru|
|**long**|**işaretsiz kısa**|Düşük sıralı kelimeyi koru|
|**long**|**imzasız Long**|Bit modelini koru; yüksek sıralı bit, işaret biti olarak işlevi kaybeder|
|**long**|**imzasız uzun uzun**|İmza- **uzun uzun**, uzatma **uzun** uzun veya **işaretsiz** Long Long 'ı Dönüştür|
|**long**|**float**|**Float**olarak temsil eder. Long tam olarak temsil edileyemeyeceği **sürece** bazı duyarlık kaybolur.|
|**long**|**double**|**Double**olarak temsil eder. **Long** yalnızca **Double**olarak gösterilemez, bazı duyarlık kaybolur.|
|**long**|**uzun çift**|**Double**olarak temsil eder. **Long** yalnızca **Double**olarak gösterilemez, bazı duyarlık kaybolur.|
|**uzun uzun**|**char**|Düşük sıra baytını koru|
|**uzun uzun**|**short**|Düşük sıralı kelimeyi koru|
|**uzun uzun**|**long**|Düşük sıralı DWORD 'yi koru|
|**uzun uzun**|**işaretsiz karakter**|Düşük sıra baytını koru|
|**uzun uzun**|**işaretsiz kısa**|Düşük sıralı kelimeyi koru|
|**uzun uzun**|**imzasız Long**|Düşük sıralı DWORD 'yi koru|
|**uzun uzun**|**imzasız uzun uzun**|Bit modelini koru; yüksek sıralı bit, işaret biti olarak işlevi kaybeder|
|**uzun uzun**|**float**|**Float**olarak temsil eder. **Uzun süre** tam olarak gösterilemeyen, bazı duyarlık kaybolur.|
|**uzun uzun**|**double**|**Double**olarak temsil eder. **Uzun süre** tam olarak bir **Double**olarak gösterilemez, bazı duyarlık kaybolur.|
|**uzun uzun**|**uzun çift**|**Double**olarak temsil eder. **Uzun süre** tam olarak bir **Double**olarak gösterilemez, bazı duyarlık kaybolur.|

<sup>1</sup> tüm **char** girdileri, **char** türünün varsayılan olarak imzalandığını varsayar.

## <a name="see-also"></a>Ayrıca bkz.

[Atama dönüştürmeleri](../c-language/assignment-conversions.md)
