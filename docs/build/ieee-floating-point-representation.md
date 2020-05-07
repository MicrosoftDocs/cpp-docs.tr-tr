---
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
ms.openlocfilehash: bb8523256c05479b303dec66ca79caa28e7cda03
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169818"
---
# <a name="ieee-floating-point-representation"></a>IEEE Kayan Noktası Temsili

Microsoft C++ (MSVC), IEEE sayısal standartlarla tutarlıdır. IEEE-754 standardı, kayan nokta biçimlerini, donanımda gerçek sayıları göstermenin bir yolunu açıklar. MSVC derleyicisi tarafından hedeflenen donanımda gösterilebilir olan kayan noktalı sayılar için en az beş iç biçim vardır ancak derleyici yalnızca ikisini de kullanır. *Tek duyarlıklı* (4 baytlık) ve *çift duyarlıklı* (8 baytlık) biçimler MSVC içinde kullanılır. Tek duyarlık, **float**anahtar sözcüğü kullanılarak bildirilmiştir. Çift duyarlık, **Double**anahtar sözcüğü kullanılarak bildirilmiştir. IEEE standart Ayrıca, bazı C ve C++ derleyicilerinin **uzun Double** veri türü olarak uygulandığı bir *çift genişletilmiş duyarlık* (10-bayt) ve *dörtlü duyarlık* (16 baytlık) biçimi *de belirtir.* MSVC derleyicisinde, **Long Double** veri türü farklı bir tür olarak değerlendirilir, ancak depolama türü **Double**ile eşlenir. Ancak, donanım tarafından desteklenen çift genişletilmiş duyarlık (10 baytlık) biçimi de dahil olmak üzere diğer biçimleri kullanan hesaplamalar için iç ve derleme dili desteği vardır.

Değerler aşağıdaki gibi depolanır:

|Değer|Farklı depolanan|
|-----------|---------------|
|tek duyarlıklı|imza biti, 8 bit üs, 23 bit mantisinin|
|Çift duyarlıklı|imza biti, 11 bit üs, 52-bit mantisinin|
|Çift genişletilmiş duyarlık|imza biti, 15 bit üs, 64 bit mantisinin|

Tek duyarlıklı ve çift duyarlıklı biçimlerde, kesir bölümünde *mantisinin* (ve bazen *Mantis*olarak adlandırılır) olarak adlandırılan, belleğin yalnızca 23 veya 52 bit depolansa bile gerçekten 24 veya 53 bit olduğu kabul edilir. Çift genişletilmiş duyarlık biçimi aslında bu biti depolar.

Üsler, olası değerinin yarısını altına alınır. Bu, gerçek üs değeri almak için bu farkı depolanan üsden çıkarsettiğiniz anlamına gelir. Depolanan üs, sapma değerinden küçükse, aslında negatif bir üs olur.

Üsler aşağıdaki gibi taraflı bir şekilde yapılır:

|Üs|Taraflı|
|--------------|---------------|
|8 bit (tek duyarlıklı)|127|
|11 bit (çift duyarlıklı)|1023|
|15 bit (çift genişletilmiş duyarlık)|16383|

Bu üsler on üstür değildir; ikisi de iki üsüslerdir. Diğer bir deyişle, 8 bit depolanan üsler-127 ile 127 arasında, 0 ile 254 arasında depolanabilir. 2<sup>127</sup> değeri kabaca, tek duyarlıklı gerçek limiti olan 10<sup>38</sup>ile eşdeğerdir.

Mantisinin 1.XXX... biçiminin ikili bir kesri olarak depolanır. Bu kesir 1 ' den büyük veya buna eşit ve 2 ' den küçük bir değere sahip. Gerçek sayıların her zaman *normalleştirilmiş biçimde*depolandığını unutmayın; diğer bir deyişle, mantisinin, mantisinin 'ın yüksek sıra biti her zaman 1 olacak şekilde sola kaydır. Bu bit her zaman 1 olduğundan, tek duyarlıklı ve çift duyarlıklı biçimlerde (depolanmaz) varsayılır. İkili (ondalık değil) noktasının yalnızca önünde 1 ' in sağında olduğu varsayılır.

Böylece, çeşitli boyutlar için aşağıdaki şekildedir:

|Biçimlendir|bayt 1|Byte 2|byte 3|bayt 4|...|bayt n|
|------------|------------|------------|------------|------------|---------|------------|
|tek duyarlıklı| `SXXXXXXX`|`XMMMMMMM`|`MMMMMMMM`|`MMMMMMMM`|||
|Çift duyarlıklı|`SXXXXXXX`|`XXXXMMMM`|`MMMMMMMM`|`MMMMMMMM`|...|`MMMMMMMM`|
|Çift genişletilmiş duyarlık|`SXXXXXXX`|`XXXXXXXX`|`1MMMMMMM`|`MMMMMMMM`|...|`MMMMMMMM`|

`S`işaret bitini temsil eder, bu `X`, ' nin taraflı üs bitleridir ve `M`mantisinin bitleridir. En soldaki bit tek duyarlıklı ve çift duyarlıklı biçimlerde varsayılır, ancak çift genişletilmiş duyarlık biçiminin byte 3 ' de "1" olarak mevcuttur.

İkili noktayı düzgün bir şekilde kaydırmak için, öncelikle üs değeri kaldırır ve ardından ikili noktayı sağ veya uygun bit sayısının soluna taşıyın.

## <a name="special-values"></a>Özel değerler

Kayan nokta biçimleri, özel olarak değerlendirilen bazı değerleri içerir.

### <a name="zero"></a>Sıfır

Sıfır değeri normalleştirilemez, bu da tek duyarlıklı veya çift duyarlıklı bir değer olan normalleştirilmiş biçimde tablo haline gelir. Tüm sıfırlardan oluşan özel bir bit deseninin 0 olduğunu temsil eder. -0 ' ı işaret biti kümesiyle sıfır olarak temsil etmek de mümkündür, ancak-0 ve 0 her zaman eşit olarak karşılaştırılır.

### <a name="infinities"></a>Sonsuz

+ ∞ Ve − ∞ değerleri, hepsi tümünün bir üsünden ve tüm sıfırların mantisinin ile temsil edilir. Hem pozitif hem de negatif sonsuz, işaret biti kullanılarak temsil edilebilir.

### <a name="subnormals"></a>Alt Normals

En küçük normalleştirilmiş sayıdan daha küçük olan sayıları temsil etmek mümkündür. Bu sayılar *alt normal* veya *denormal* sayı olarak bilinir. Üs tümünün sıfırıncı ve mantisinin sıfır olmayan bir değer ise, mantisinin 'in örtük önünde bir bit değeri sıfır olarak değerlendirilir. Alt normal sayıların duyarlığı, mantisinin ' deki önde gelen sıfır sayısı kaldığında aşağı gider.

### <a name="nan---not-a-number"></a>NaN-sayı değil

IEEE kayan nokta biçiminde 0/0 gibi gerçek sayı olmayan değerleri temsil etmek mümkündür. Bu türden bir değere *Nan*adı verilir. Bir NaN, hepsi bir üssün ve sıfır olmayan bir mantisinin temsil edilir. İki tür NaNs, *sessiz* nans, veya qnans, ve nans veya snans *sinyalleri* vardır. Sessiz NaNs, mantisinin içinde önde gelen bir ifadedir ve genellikle bir ifade aracılığıyla dağıtılır. Sonsuz bir değeri temsil eder, sonsuz ile bölme sonucu veya sonsuz değeri sıfıra çarpar. NaNs sinyalin mantisinin içinde önünde sıfır var. Bunlar, kayan nokta donanım özel durumuna işaret etmek için geçerli olmayan işlemler için kullanılır.

## <a name="examples"></a>Örnekler

Aşağıda, tek duyarlıklı biçimdeki bazı örnekler verilmiştir:

- 2 değeri için, işaret biti sıfırdır ve depolanan üs, 128 veya 1000 0000 ' dir. Bu, 127 ve 1 ' dir. Depolanan ikili mantisinin, örtük 1 ve ikili noktası olan (1.) 000 0000 0000 0000 0000 0000, bu nedenle gerçek mantisinin bir tane olur.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |2|1 * 2<sup>1</sup>|0100 0000 0000 0000 0000 0000 0000 0000|0x40000000|

- -2 değeri. İşaret bitinin ayarlanmış olması dışında + 2 ile aynıdır. Bu, tüm IEEE biçimli kayan noktalı sayıların negatifi için geçerlidir.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |-2|-1 * 2<sup>1</sup>|1100 0000 0000 0000 0000 0000 0000 0000|0xC0000000|

- 4 değeri. Aynı mantisinin, üs, bir artar (taraflı değer 129 veya ikili içinde 100 0000 1).

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |4|1 * 2<sup>2</sup>|0100 0000 1000 0000 0000 0000 0000 0000|0x40800000|

- 6 değeri. Aynı üs, mantisinin daha büyük; (1.) 100 0000... 0000 0000, bu ikili bir kesir olduğundan, kesirli basamakların değerleri 1/2, 1/4, 1/8 ve benzeri olduğundan 1 1/2 ' dir.

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
   |2,5|1,25 * 2<sup>1</sup>|0100 0000 0010 0000 0000 0000 0000 0000|0x40200000|

- 1/10, ikili içindeki yinelenen bir kesrin. Mantisinin yalnızca 1,6 ' dir ve taraflı üs, 1,6 ' nin 16 ' ya bölüneceğini söyler 011 1101 1 (ondalık olarak 123). Gerçek üs 123-127 =-4 ' dür, bu da çarpılacak faktörün 2<sup>-4</sup> = 1/16 olduğunu gösterir. Saklı mantisinin, en son bit içinde yuvarlandığına, gösterilemeyen bir sayıyı mümkün olduğunca doğru bir şekilde temsil etmeye çalışır. (1/10 ve 1/100 ' nin ikili dosya içinde tam olarak gösterilemeyen nedeni, 1/3 tam olarak ondalık olarak gösterilemeyen bir tablo değildir.)

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |0.1|1,6 * 2<sup>-4</sup>|0011 1101 1100 1100 1100 1100 1100 1101|0x3DCCCCCD|

- Sıfır, en az olası gösterilemeyen pozitif değer olan formülü kullanan özel bir durumdur.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |0|1 * 2<sup>-128</sup>|0000 0000 0000 0000 0000 0000 0000 0000|0x00000000|

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Noktalı Sayıların Neden Duyarlık Kaybedebileceği](why-floating-point-numbers-may-lose-precision.md)
