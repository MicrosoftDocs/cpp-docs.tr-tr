---
description: 'Daha fazla bilgi edinin: IEEE Floating-Point temsili'
title: IEEE Kayan Noktası Temsili
ms.date: 05/06/2019
helpviewer_keywords:
- float keyword
- real*8 value
- floating-point numbers, IEEE representation
- double data type, floating-point representation
- IEEE floating point representation
- real*10 value
- long double
- real*4 value
ms.assetid: 537833e8-fe05-49fc-8169-55fd0314b195
ms.openlocfilehash: 9de48975ba13fae6117b095565f22265e28edf07
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162657"
---
# <a name="ieee-floating-point-representation"></a>IEEE Kayan Noktası Temsili

Microsoft C++ (MSVC), IEEE sayısal standartlarla tutarlıdır. IEEE-754 standardı, kayan nokta biçimlerini, donanımda gerçek sayıları göstermenin bir yolunu açıklar. MSVC derleyicisi tarafından hedeflenen donanımda gösterilemeyen, kayan noktalı sayılar için en az beş iç biçim vardır. Derleyici yalnızca ikisini de kullanır. *Tek duyarlıklı* (4 baytlık) ve *çift duyarlıklı* (8 baytlık) biçimler MSVC içinde kullanılır. Tek duyarlık anahtar sözcüğü kullanılarak bildirilmiştir **`float`** . Çift duyarlık anahtar sözcüğü kullanılarak bildirilmiştir **`double`** . IEEE standardı Ayrıca *yarı duyarlık* (2 baytlık) ve *dörtlü duyarlık* (16 baytlık) biçimlerini ve bazı C ve C++ derleyicilerinin veri türü olarak uygulayabileceği bir *çift genişletilmiş duyarlık* (10 baytlık) biçimi de belirtir **`long double`** . MSVC derleyicisinde, **`long double`** veri türü farklı bir tür olarak değerlendirilir, ancak depolama türü ile eşlenir **`double`** . Bununla birlikte, donanım tarafından desteklenen çift genişletilmiş duyarlık biçimi de dahil olmak üzere diğer biçimleri kullanan hesaplamalar için iç ve derleme dili desteği vardır.

Değerler aşağıdaki gibi depolanır:

|Değer|Farklı depolanan|
|-----------|---------------|
|tek duyarlıklı|imza biti, 8 bit üs, 23 bit mantisinin|
|Çift duyarlıklı|imza biti, 11 bit üs, 52-bit mantisinin|

Tek duyarlıklı ve çift duyarlıklı biçimlerdeki kesirli bölümünde önde gelen 1 ' de bir varsayılır. Kesirli parçaya *mantisinin* denir (bazen *Mantis* olarak bilinir). Bu önde gelen 1 bellekte depolanmaz, bu nedenle katsayılar gerçekten 24 veya 53 bittir, ancak bir daha az bit depolansa bile. Çift genişletilmiş duyarlık biçimi aslında bu biti depolar.

Üsler, olası değerinin yarısını altına alınır. Gerçek üs değeri almak için bu farkı depolanan üsden çıkarsbir hale getirmek anlamına gelir. Depolanan üs, sapma değerinden küçükse, aslında negatif bir üs olur.

Üsler aşağıdaki gibi taraflı bir şekilde yapılır:

|Üs|Taraflı|
|--------------|---------------|
|8 bit (tek duyarlıklı)|127|
|11 bit (çift duyarlıklı)|1023|

Bu üsler on üsleri değildir; ikisi de iki üsüsleri olur. Diğer bir deyişle, 8 bit depolanan üsler-127 ile 127 arasında, 0 ile 254 arasında depolanabilir. 2<sup>127</sup> değeri kabaca, tek duyarlıklı gerçek limiti olan 10<sup>38</sup>ile eşdeğerdir.

Mantisinin 1.XXX... biçiminin ikili bir kesri olarak depolanır. Bu kesir 1 ' den büyük veya buna eşit ve 2 ' den küçük bir değere sahip. Gerçek sayılar her zaman *normalleştirilmiş biçimde* depolanır. Diğer bir deyişle, mantisinin, mantisinin 'ın yüksek sıra biti her zaman 1 olacak şekilde sola kaydır. Bu bit *her zaman* 1 olduğundan, tek duyarlıklı ve çift duyarlıklı biçimlerdeki (depolanmamış) varsayılır. İkili (ondalık değil) noktasının yalnızca önünde 1 ' in sağında olduğu varsayılır.

Kayan nokta gösteriminin biçimi aşağıdaki gibidir:

|Biçimlendir|bayt 1|Byte 2|byte 3|bayt 4|...|bayt n|
|------------|------------|------------|------------|------------|---------|------------|
|tek duyarlıklı| `SXXXXXXX`|`XMMMMMMM`|`MMMMMMMM`|`MMMMMMMM`|||
|Çift duyarlıklı|`SXXXXXXX`|`XXXXMMMM`|`MMMMMMMM`|`MMMMMMMM`|...|`MMMMMMMM`|

`S` işaret bitini temsil eder, bu, ' `X` nin taraflı üs bitleridir ve `M` mantisinin bitleridir. En soldaki bit tek duyarlıklı ve çift duyarlıklı biçimlerde varsayılır.

İkili noktayı düzgün bir şekilde kaydırmak için, öncelikle üs değeri kaldırır ve ardından ikili noktayı sağ veya uygun bit sayısının soluna taşıyın.

## <a name="special-values"></a>Özel değerler

Kayan nokta biçimleri, özel olarak değerlendirilen bazı değerleri içerir.

### <a name="zero"></a>Sıfır

Sıfır, tek duyarlıklı veya çift duyarlıklı bir değerin normalleştirilmiş biçiminde olmayan bir tablo haline gelen Normalleştirilmemiş olamaz. Tüm sıfırlardan oluşan özel bir bit deseninin 0 olduğunu temsil eder. -0 ' ı işaret biti kümesiyle sıfır olarak temsil etmek de mümkündür, ancak-0 ve 0 her zaman eşit olarak karşılaştırılır.

### <a name="infinities"></a>Sonsuz

+ ∞ Ve − ∞ değerleri, hepsi tümünün bir üsünden ve tamamen sıfır olan bir mantisinin ile temsil edilir. Pozitif ve negatif, işaret biti kullanılarak temsil edilir.

### <a name="subnormals"></a>Alt Normals

Normalleştirilmiş biçimdeki en küçük sayıdan daha küçük olan sayıları temsil etmek mümkündür. Bunlar *alt normal* veya *denormal* sayı olarak adlandırılırlar. Üs tümünün sıfırıncı ve mantisinin sıfır olmayan bir değer ise, mantisinin 'in örtük önünde bir bit değeri sıfır olarak değerlendirilir. Alt normal sayıların duyarlığı, mantisinin ' deki önde gelen sıfır sayısı kaldığında aşağı gider.

### <a name="nan---not-a-number"></a>NaN-sayı değil

IEEE kayan nokta biçiminde 0/0 gibi gerçek sayı olmayan değerleri temsil etmek mümkündür. Bu türden bir değere *Nan* adı verilir. Bir NaN, hepsi bir üssün ve sıfır olmayan bir mantisinin temsil edilir. İki tür NaNs, *sessiz* nans, veya qnans, ve nans veya snans *sinyalleri* vardır. Sessiz NaNs, mantisinin içinde önde gelen bir ifadeye sahiptir ve bir ifadeyle yayılamaz. Sonsuz bir değeri temsil eder, sonsuz ile bölme sonucu veya sonsuz değeri sıfıra çarpar. NaNs sinyalin mantisinin içinde önünde sıfır var. Bunlar, kayan nokta donanım özel durumu sinyali vermek için geçerli olmayan işlemler için kullanılırlar.

## <a name="examples"></a>Örnekler

Aşağıda, tek duyarlıklı biçimdeki bazı örnekler verilmiştir:

- 2 değeri için, işaret biti sıfırdır. Depolanan üs, 128 veya 1000 0000 ' dir. Bu, 127 ve 1 ' dir. Depolanan ikili mantisinin, örtük 1 ve ikili noktası olan (1.) 000 0000 0000 0000 0000 0000, bu nedenle gerçek mantisinin bir tane olur.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |2|1 * 2<sup>1</sup>|0100 0000 0000 0000 0000 0000 0000 0000|0x40000000|

- -2 değeri. İşaret bitinin ayarlanmış olması dışında + 2 ile aynıdır. Aynı şey, tüm IEEE biçimli kayan noktalı sayıların negatif değeri için de geçerlidir.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |-2|-1 * 2<sup>1</sup>|1100 0000 0000 0000 0000 0000 0000 0000|0xC0000000|

- 4 değeri. Aynı mantisinin, üs, bir artar (taraflı değer 129 veya ikili içinde 100 0000 1).

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |4|1 * 2<sup>2</sup>|0100 0000 1000 0000 0000 0000 0000 0000|0x40800000|

- 6 değeri. Aynı üs, mantisinin daha büyük. Bu, (1.) 100 0000... 0000 0000, bir ikili kesir olduğundan, kesirli basamakların değerleri 1/2, 1/4, 1/8 ve benzeri olduğundan 1 1/2.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |6|1,5 * 2<sup>2</sup>|0100 0000 1100 0000 0000 0000 0000 0000|0x40C00000|

- 1 değeri. İki farklı üsleri ile aynı mantisinin, taraflı üs, 127 veya ikili içindeki 011 1111 1 ' den az bir küçüktür.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |1|1 * 2<sup>0</sup>|0011 1111 1000 0000 0000 0000 0000 0000|0x3F800000|

- 0,75 değeri. Taraflı üs değeri 126, 011 1111 0 binary ve mantisinin (1.) 100 0000... 0000 0000, 1 1/2 ' dir.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |0,75|1,5 * 2<sup>-1</sup>|0011 1111 0100 0000 0000 0000 0000 0000|0x3F400000|

- 2,5 değeri. 1/4 'yi temsil eden bit, mantisinin içinde ayarlandığı sürece tamamen iki ile aynıdır.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |2.5|1,25 * 2<sup>1</sup>|0100 0000 0010 0000 0000 0000 0000 0000|0x40200000|

- 1/10, ikili içindeki yinelenen bir kesrin. Mantisinin çok az 1,6 ve taraflı üs, 1,6 ' nin 16 ' ya bölüneceğini söyler. (Ondalık olarak 123 olan 011 1101 1.) Gerçek üs 123-127 =-4 ' dür, bu da çarpılacak faktörün 2<sup>-4</sup> = 1/16 olduğunu gösterir. Depolanan mantisinin, en uygun şekilde, gösterilemeyen sayıyı en doğru şekilde temsil etmeye yönelik son bit içinde yuvarlanır. (1/10 ve 1/100 olmasının nedeni, ikili dosya içinde tam olarak gösterilemeyen, 1/3 de ondalık olarak tam olarak gösterilemeyen bir tablo olma nedenidir.)

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |0.1|1,6 * 2<sup>-4</sup>|0011 1101 1100 1100 1100 1100 1100 1101|0x3DCCCCCD|

- Sıfır özel bir durumdur. Bu, tüm sıfırlanmış olabilecek en düşük gösterilebilir tablo pozitif değeri için formülü kullanır.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |0|1 * 2<sup>-128</sup>|0000 0000 0000 0000 0000 0000 0000 0000|0x00000000|

## <a name="see-also"></a>Ayrıca bkz.

[Floating-Point sayıların neden duyarlık Kaybedemeyebilir](why-floating-point-numbers-may-lose-precision.md)
