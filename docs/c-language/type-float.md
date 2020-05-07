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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346333"
---
# <a name="type-float"></a>Tür float

Kayan nokta numaraları IEEE (elektrik ve Elektronik Mühendisleri Enstitüsü) biçimini kullanır. Float türüne sahip tek duyarlıklı değerler 4 bayttır, bir işaret biti, 8 bit fazla 127 ikili üs ve 23 bit Mantis oluşur. Mantis, 1,0 ile 2,0 arasında bir sayıyı temsil eder. Mantis öğesinin üst sıra biti her zaman 1 olduğundan, bu numara sayı içinde depolanmaz. Bu gösterim, float türü için yaklaşık 3.4 E-38 ile 3.4 E + 38 arasında bir Aralık verir.

Uygulamanızın ihtiyaçlarına bağlı olarak, değişkenleri float veya Double olarak bildirebilirsiniz. İki tür arasındaki asıl farklılıklar, temsil ettikleri öneme, gereken depolama alanını ve bunların aralığını temsil eder. Aşağıdaki tabloda, anlam ve depolama gereksinimleri arasındaki ilişki gösterilmektedir.

### <a name="floating-point-types"></a>Kayan nokta türleri

|Tür|Önemli basamaklar|Bayt sayısı|
|----------|------------------------|---------------------|
|float|6 - 7|4|
|double|15 - 16|8|

Kayan nokta değişkenleri, sayının değerini içeren bir Mantis ile temsil edilir ve sayının büyüklük sırasını içeren bir üs değeri.

Aşağıdaki tabloda, her kayan nokta türü için Mantis ve üs için ayrılan bit sayısı gösterilmektedir. Herhangi bir float veya Double 'un en önemli biti her zaman işaret bitidir. 1 ise, sayı negatif kabul edilir; Aksi takdirde, pozitif bir sayı olarak kabul edilir.

### <a name="lengths-of-exponents-and-mantissas"></a>Üslerin ve Mantisler uzunluklarının uzunluğu

|Tür|Üs uzunluğu|Mantis uzunluğu|
|----------|---------------------|---------------------|
|float|8 bit|23 bit|
|double|11 bit|52 bit|

Üs değerleri işaretsiz bir biçimde depolandığından üs, olası değeri yarıya kadar taraflı olur. Float türü için, sapma 127; Double türü için 1023 olur. Üs değerinden sapma değerini çıkararak gerçek üs değerini hesaplamanız sağlayabilirsiniz.

Mantis, 1 ' den büyük veya buna eşit ve 2 ' den küçük bir ikili kesir olarak depolanır. Float ve Double türleri için, en önemli bit konumunda Mantis önünde bir önde gelen 1 bulunur; bu nedenle, en önemli bit hiçbir zaman bellekte depolanmasa bile, Mantisler aslında 24 ve 53 bit uzunluğundadır.

Yalnızca açıklanan depolama yöntemi yerine, kayan nokta paketi, ikili kayan nokta numaralarını, Normalleştirilmemiş sayı olarak saklayabilir. "Normalleştirilmemiş sayılar", Mantis 'in en önemli bitinin 0 olduğu ayrılmış üs değerleri olan sıfır olmayan kayan noktalı sayılardır. Denormallanmış biçimi kullanarak, kayan noktalı bir sayının aralığı duyarlık maliyetinde genişletilebilir. Kayan noktalı bir sayının normalleştirilmiş veya Normalleştirilmemiş biçimde temsil edilip edilmeyeceğini kontrol etmezsiniz; kayan nokta paketi temsili belirler. Değer, Normalleştirilmemiş bir biçimde gösterilebilen en düşük değerden daha küçük hale gelinceye kadar, kayan nokta paketi hiçbir şekilde hiç bir şekilde kullanılamaz.

Aşağıdaki tabloda her kayan nokta türünün değişkenlerinde depolayabileceği minimum ve maksimum değerler gösterilmektedir. Bu tabloda listelenen değerler yalnızca normalleştirilmiş kayan nokta numaraları için geçerlidir; yoğun kayan noktalı sayıların en küçük değeri daha küçüktür. 80*x*87 yazmaçlarında tutulan sayıların her zaman 80-bit normalleştirilmiş biçimde temsil edileceğini unutmayın; sayılar yalnızca 32 bit veya 64 bit kayan nokta değişkenlerinde (float ve Type Long türündeki değişkenler) depolanırken, Normalleştirilmemiş biçimde gösterilebilir.

### <a name="range-of-floating-point-types"></a>Kayan nokta türleri aralığı

|Tür|En küçük değer|En büyük değer|
|----------|-------------------|-------------------|
|float|1,175494351 E-38|3,402823466 E + 38|
|double|2.2250738585072014 E-308|1.7976931348623158 E + 308|

Duyarlık depolamanın bir kaygısını kullanıyorsa, kayan nokta değişkenleri için float türünü kullanmayı düşünün. Bunun tersine, duyarlık en önemli ölçüttür ise Double türü kullanın.

Kayan nokta değişkenleri, daha fazla anlam türüne yükseltilebilir (float türünden Double türüne). Yükseltme genellikle kayan nokta değişkenlerinde aritmetik gerçekleştirdiğinizde oluşur. Bu aritmetik, en yüksek duyarlık derecesine sahip değişken kadar yüksek bir duyarlık derecesi olarak her zaman yapılır. Örneğin, aşağıdaki tür bildirimlerini göz önünde bulundurun:

```
float f_short;
double f_long;
long double f_longer;

f_short = f_short * f_long;
```

Yukarıdaki örnekte, değişkeni `f_short` , Double ve çarpılarak `f_long`türüne yükseltilir; Sonuç olarak `f_short`, kendisine atanmadan önce float türüne yuvarlanır.

Aşağıdaki örnekte (önceki örnekteki bildirimleri kullanan) aritmetik (32-bit), değişkenler üzerinde float (bit) duyarlıkta yapılır; sonuç daha sonra Double türüne yükseltilir:

```
f_longer = f_short * f_short;
```

## <a name="see-also"></a>Ayrıca bkz.

[Temel türlerin depolanması](../c-language/storage-of-basic-types.md)
