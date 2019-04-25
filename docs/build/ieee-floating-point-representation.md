---
title: IEEE Kayan Noktası Temsili
ms.date: 11/04/2016
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
ms.openlocfilehash: 69686e7e1c8994b799607eebf7e50387ed688272
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188840"
---
# <a name="ieee-floating-point-representation"></a>IEEE Kayan Noktası Temsili

Microsoft Visual C++ IEEE sayısal standartları ile uyumludur. Standart IEEE 754 kayan nokta biçimleri, donanım gerçek sayıları temsil etmek için bir yol açıklar. MSVC derleyici tarafından hedeflenen donanımda gösterilebilir bir kayan noktalı sayılar için en az beş iç biçimleri vardır, ancak derleyicinin yalnızca iki tanesi kullanır. *Tek duyarlıklı* (4-bayt) ve *çift duyarlıklı* biçimleri (8 bayt), Visual C++'da kullanılır. Tek duyarlıklı anahtar sözcüğü kullanılarak bildirilen **float**. Çift duyarlıklı anahtar sözcüğü kullanılarak bildirilen **çift**. IEEE standardı ayrıca belirtir *yarı çift duyarlıklı* (2 baytlık) ve *dört duyarlıklı* (16 baytlık) biçimleri yanı sıra bir *çift genişletilmiş duyarlık* (10 bayt) Bazı C ve C++ Derleyicileri olarak uygulayan bir biçim **uzun çift** veri türü. MSVC derleyicisi, **uzun çift** veri türü farklı bir tür kabul edilir, ancak depolama türü eşleyen **çift**. Yoktur, ancak, iç ve derleme dili desteği genişletilmiş-duyarlıklı (10 bayt) biçimi de dahil olmak üzere diğer biçimlerini kullanarak hesaplamalar için donanım tarafından desteklenen burada.

Değerleri şu şekilde depolanır:

|Değer|Olarak depolanır|
|-----------|---------------|
|tek duyarlıklı|bit, 8 bitlik üs, 23 bit anlam oturum açın.|
|çift duyarlık|bit, 11 bit üssü, 52 bit anlam oturum açın.|
|çift genişletilmiş duyarlık|bit, üs 15-bit, 64-bit anlam oturum açın.|

Tek duyarlık hem çift duyarlık biçimlerde adlı kesirli bölümü içinde bir varsayılan satır aralığı 1 yoktur *anlam* (ve bazen denir *Mantis*), diğer bir deyişle depolanan değil yalnızca 23 veya 52 bit depolanan olsa bile katsayılar gerçekten 24 veya 53 bit, böylece bellek. Genişletilmiş-duyarlıklı biçimi, aslında bu bit depolar.

Üsler olası değerlerine yarısını güçlü eğilimi nedeniyle. Bu, bu sapması gerçek üs almak için saklı üs gelen çıkarma anlamına gelir. Saklı üs sapması'dan küçük, negatif üssünün gerçekten olur.

Üsler gibi ağırlıklı:

|Üs|Tarafından ağırlıklı|
|--------------|---------------|
|8-bit (tek duyarlıklı)|127|
|11-bit (çift duyarlıklı)|1023|
|15-bit (Genişletilmiş-duyarlıklı)|16383|

Bu üsler katları değildir; powers iki değildirler. Diğer bir deyişle, 8 bitlik saklı üsler-127 0 en fazla 254 depolanan 127 değişebilir. ' % S'değeri 2<sup>127</sup> 10 kabaca eşdeğerdir<sup>38</sup>, tek duyarlıklı gerçek sınırını olduğu.

Anlam formun ikili bir kesir olarak depolanan 1.XXX.... Bu bölümü, büyüktür veya eşittir 1 ve 2'den küçük bir değere sahip. Gerçek sayıları, her zaman depolandığını unutmayın *formu normalleştirilmiş*; diğer bir deyişle, anlam sol-yüksek sıralı bitten anlam, her zaman 1'dir, kaydırılacağı uzaklık. Bu bit her zaman 1 olduğundan (depolanmayan) varsayılır tek duyarlık hem çift duyarlık biçimde. İkili (ondalık değil) noktası yalnızca önde gelen 1 sağında varsayılır.

Biçim sonra çeşitli boyutları şu şekildedir:

|Biçimi|1 bayt|2 bayt|Bayt 3|4 bayt|...|bayt n|
|------------|------------|------------|------------|------------|---------|------------|
|tek duyarlıklı| `SXXXXXXX`|`XMMMMMMM`|`MMMMMMMM`|`MMMMMMMM`|||
|çift duyarlık|`SXXXXXXX`|`XXXXMMMM`|`MMMMMMMM`|`MMMMMMMM`|...|`MMMMMMMM`|
|çift genişletilmiş duyarlık|`SXXXXXXX`|`XXXXXXXX`|`1MMMMMMM`|`MMMMMMMM`|...|`MMMMMMMM`|

`S` İmza biti temsil `X`'s popülasyon üs bitleri ve `M`'s anlam bitleri. En soldaki bit tek duyarlık hem çift duyarlık biçimlerde kabul edilir, ancak "1" mevcut bayt çift genişletilmiş duyarlık biçimi 3 unutmayın.

İkili noktasının düzgün bir şekilde geçiş yapmak için ilk üs unbias ve ardından ikili noktasının sağa taşıyın veya uygun bit sayısı kadar sola.

## <a name="special-values"></a>Özel değerler

Kayan nokta özel olarak kabul edilen bazı değerler biçimler.

### <a name="zero"></a>Sıfır

Sıfır, hangi çıkarıldığında bir tek duyarlıklı veya çift duyarlık değeri normalleştirilmiş biçiminde kolaylaştırır normalleştirilmesine olamaz. Sıfır, bir özel bir bit desenine 0 temsil eder. Ayrıca temsil etmek için - 0 işaretiyle sıfır olarak biti ayarlanmamış, ancak - 0 ve 0 her zaman eşit olarak karşılaştırın.

### <a name="infinities"></a>Sonsuz

+ ∞ ve −∞ değerleri üs tümüyle ve sıfır mantisinin tarafından temsil edilir. Pozitif ve negatif sonsuz imza biti kullanarak temsil edilebilir.

### <a name="subnormals"></a>Subnormals

En küçük normalleştirilmiş sayıdan küçük büyüklük numaralarını temsil etmek mümkündür. Bu sayı olarak da bilinir *subnormal* veya *denormal* sayı. Üs sıfır ve sıfır olmayan katsayıdır, anlam örtük önde gelen biti sıfır, bir kabul edilir. Duyarlık subnormal sayıların arıza olarak anlam 2f3b sayısı artar.

### <a name="nan---not-a-number"></a>NaN - sayı değil

0 gibi bir gerçek sayı olmayan değerleri temsil etmek mümkündür / 0, IEEE kayan nokta biçiminde. Bu tür bir değer olarak adlandırılan bir *NaN*. Tüm yorumlar ve sıfır olmayan bir anlam bir üs bir NaN temsil edilir. İki tür NaN'ler, *sessiz* NaN'ler veya QNaNs, ve *sinyal* NaN'ler veya SNaNs. Sessiz NaN'ler önde gelen bir anlam olması ve genellikle bir ifade dağıtılır. Bunlar, sonsuzluk bölme ya da sıfıra sonsuzluk çarparak sonucu gibi belirsiz bir değeri temsil eder. Kanalın NaN'ler anlam başında sıfır var. Bunlar, bir kayan nokta donanım özel durumu sinyal için geçerli olmayan işlemler için kullanılır.

## <a name="examples"></a>Örnekler

Aşağıda bazı örnekler tek duyarlıklı biçiminde verilmiştir:

- Değer 2 için imza biti sıfırdır ve 128 saklı üstür veya ikili, 1000 0000 127 artı 1 olduğu. Depolanan ikili (1) katsayıdır 000 0000 0000 0000 0000 1 ve ikili örtük bir lider olan 0000, gerçek bir katsayıdır şekilde gelin.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |2|1 * 2<sup>1</sup>|0100 0000 0000 0000 0000 0000 0000 0000|0x40000000|

- Değer -2. İmza biti ayarlanmış olması dışında + 2 aynıdır. Bu tüm IEEE kayan nokta sayıları biçimlendirme eksi işareti için geçerlidir.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |-2|-1 * 2<sup>1</sup>|1100 0000 0000 0000 0000 0000 0000 0000|0xC0000000|

- 4 değeri. Aynı anlam üs (popülasyon 129 veya 100 0000 1 ikili değerdir. tek artırır.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |4|1 * 2<sup>2</sup>|0100 0000 1000 0000 0000 0000 0000 0000|0x40800000|

- Değer 6. Aynı üs katsayıdır yarı oranında daha büyük — onun (1.) 100 0000 ... Bu ikili bir kesir olduğundan 0000 0000, kesirli basamaklar değerleri 1/2, 1/4, 1/8 ve benzeri olduğundan, 1 1/2 değerindedir.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |6|1.5 * 2<sup>2</sup>|0100 0000 1100 0000 0000 0000 0000 0000|0x40C00000|

- 1 değeri. Diğer iki taraflı üs olarak aynı anlam ikiden az 127 ya da ikili 011 1111 1 biridir.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |1.|1 * 2<sup>0</sup>|0011 1111 1000 0000 0000 0000 0000 0000|0x3F800000|

- 0,75 değeri. 126 popülasyon üstür 011 1111 0 içinde ikili ve anlam olduğunu (1.) 100 0000 ... 0000 0000 1 1/2'dir.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |0.75|1.5 * 2<sup>-1</sup>|0011 1111 0100 0000 0000 0000 0000 0000|0x3F400000|

- 2.5 değeri. Anlam içinde tam olarak aynı iki dışındaki 1/4 temsil eden bir bit ayarlanır.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |2,5|1.25 * 2<sup>1</sup>|0100 0000 0010 0000 0000 0000 0000 0000|0x40200000|

- 1/10 ikili yinelenen bir bölümüdür. 1.6 yalnızca çekingen katsayıdır ve popülasyon üs 1.6 16 tarafından Bölünecek olduğunu söylüyor (011 1101 1 ondalık 123 olan ikili değer). 123-127 true üstür = - çarpmak istediğiniz faktörü 2 olduğu anlamına gelir 4,<sup>-4</sup> = 1/16. Saklı anlam son bit yuvarlanır Not — denemesi çıkarıldığında sayısını mümkün olduğunca doğru bir şekilde temsil eder. (Nedeni 1/10 ile 1/100 ikili gösterilebilir değil, tam olarak 1/3 tam olarak ondalık biçimde gösterilebilir olmasının nedeni benzer.)

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |0.1|1.6 * 2<sup>-4</sup>|0011 1101 1100 1100 1100 1100 1100 1101|0x3DCCCCCD|

- Sıfır sıfır olan minimum olası gösterilebilir pozitif değer, formülü kullanan özel bir durumdur.

   |Değer|Formül|İkili gösterim|Onaltılık|
   |-|-|-|-|
   |0|1 * 2<sup>-128</sup>|0000 0000 0000 0000 0000 0000 0000 0000|0x00000000|

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Noktalı Sayıların Neden Duyarlık Kaybedebileceği](why-floating-point-numbers-may-lose-precision.md)