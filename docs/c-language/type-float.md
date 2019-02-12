---
title: Tür float
ms.date: 11/04/2016
helpviewer_keywords:
- type float
- exponent length
- float keyword [C]
- mantissas, length
- floating-point numbers, float type
- ranges, floating-point types
- floating-point numbers, variables
- lengths, mantissa
- double data type, type float
- IEEE floating-point representation
- lengths, exponent
ms.assetid: 706e332b-17a0-4a30-b7d8-5d6cd372524b
ms.openlocfilehash: 61bfd094801165e0c3e41e5de6fcbfb0c5e59504
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56151279"
---
# <a name="type-float"></a>Tür float

Kayan nokta sayıları IEEE (Institute of Electrical and Electronics Engineers) biçimini kullanın. Float türü olan tek duyarlıklı değerler 4 bayt, imza biti, 8 bitlik aşırı 127 ikili üs ve 23 bit Mantis oluşan vardır. Mantis 1.0 ve 2.0 arasında bir sayı temsil eder. Yüksek sıralı bitten Mantis, her zaman 1 olduğundan, sayısında depolanmaz. Bu gösterim bir dizi yaklaşık 3.4e sağlar-38 3.4e + 38 için tür float olarak.

Değişkenleri, float veya double, uygulamanızın ihtiyaçlarına bağlı olarak bildirebilirsiniz. İki türü arasındaki asıl farklılıklar temsil ettikleri önemi, gereksinim duydukları depolama ve menzil ' dir. Aşağıdaki tablo, önem ve depolama alanı gereksinimleri arasındaki ilişkiyi gösterir.

### <a name="floating-point-types"></a>Kayan nokta türleri

|Tür|Önemli basamak|Bayt sayısı|
|----------|------------------------|---------------------|
|float|6 - 7|4|
|çift|15 - 16|8|

Kayan nokta değişkenleri sayısını ve sayının büyüklük sırası içeren bir üs değerini içeren bir Mantis tarafından temsil edilir.

Aşağıdaki tabloda, Mantis ve her bir kayan nokta türü için ayrılan bit sayısını gösterir. Her zaman herhangi bir float veya double en anlamlı bit imza biti ' dir. 1. sayı negatif kabul edilir; Aksi takdirde, pozitif bir sayı olarak kabul edilir.

### <a name="lengths-of-exponents-and-mantissas"></a>Üsler ve Mantisler uzunluğu

|Tür|Üs uzunluğu|Mantissa length|
|----------|---------------------|---------------------|
|float|8 bit|23 bit|
|çift|11 bit|52 bit|

Üsler işaretsiz bir biçimde saklandığından, üs yarım olası değer tarafından Eğimli. Tür float için 127 sapması ise; double türü için buna 1023 var. Gerçek üs değeri, üs GMT'den değer çıkararak hesaplayabilirsiniz.

Mantis büyüktür veya eşittir 1 ve 2'den ikili bir kesir olarak depolanır. Türleri float ve çift yoktur başta bir 1 Mantis içinde en önemli bite konumda en önemli bite asla bellekte depolanır olsa bile mantisler gerçekten 24 ve 53 uzun, sırasıyla bittir.

Açıklanmış depolama yöntemi yerine, kayan nokta paketini ikili kayan noktalı sayıların normalleştirilmişlikten çıkarılmış bir sayı olarak depolayabilirsiniz. "Normalleştirilmişlikten çıkarılmış" sıfır olmayan bir kayan noktalı sayıların Mantis en anlamlı biti 0 olduğu ayrılmış üs değerlerle sayılardır. Normalleştirilmişlikten çıkarılmış biçimini kullanarak, bir kayan noktalı sayı aralığı, duyarlık genişletilebilir. Bir kayan noktalı sayı normalleştirilmiş veya normalleştirilmişlikten çıkarılmış biçimde temsil edilir denetleyemez; kayan nokta paketini gösterimi belirler. Kayan nokta paketini üs duruma gelmediği sürece hiçbir zaman normalleştirilmişlikten çıkarılmış bir form kullanır. normalleştirilmiş bir biçimde temsil edilebilir en küçük değerinden küçük.

Aşağıdaki tabloda, her bir kayan nokta türü değişkenlerindeki depolayabilirsiniz minimum ve maksimum değerleri gösterir. Bu tabloda listelenen değerler yalnızca normalleştirilmiş kayan nokta sayıları için geçerlidir; normalleştirilmişlikten çıkarılmış kayan noktalı sayıların, daha küçük bir en düşük değere sahip. 80 numaralı korunur sayıların Not*x*87 kayıtlar her zaman 80 bit normalleştirilmiş biçiminde temsil; numaraları yalnızca gösterilebileceği 32 bit veya 64-bit kayan nokta değişkenleri (tür float değişkenlerinin saklandığında normalleştirilmişlikten çıkarılmış biçimde ve uzun yazın).

### <a name="range-of-floating-point-types"></a>Kayan nokta türleri aralığı

|Tür|En düşük değer|En yüksek değer|
|----------|-------------------|-------------------|
|float|1.175494351 E - 38|3.402823466 E + 38|
|çift|2.2250738585072014 E - 308|1.7976931348623158 E + 308|

Duyarlık bir sorun depolama daha küçük tür float kayan nokta değişkenleri kullanmayı düşünün. Buna karşılık, duyarlık en önemli bir ölçüt ise, türü çift kullanın.

Kayan nokta değişkenleri (double türü için tür float) büyük önem türüne yükseltilebilir. Kayan nokta değişkenleri aritmetik işlemleri genellikle yükseltme gerçekleşir. Bu aritmetik her zaman yüksek düzeyde bir duyarlık duyarlık en yüksek derecede değişkenle olarak yapılabilir. Örneğin, aşağıdaki tür bildirimleri göz önünde bulundurun:

```
float f_short;
double f_long;
long double f_longer;

f_short = f_short * f_long;
```

Yukarıdaki örnekte, değişken `f_short` çift değiştirilir ve çarpılmasıyla `f_long`; sonra da sonucu için atanmadan önce tür float yuvarlanır `f_short`.

Aritmetik float (32-bit) duyarlık değişkenlerde gerçekleştirilir (önceki örnekte bildirimleri kullanır) aşağıdaki örnekte, Sonuç tür double yükseltilir:

```
f_longer = f_short * f_short;
```

## <a name="see-also"></a>Ayrıca bkz.

[Temel Türleri Depolama](../c-language/storage-of-basic-types.md)
