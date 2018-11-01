---
title: Bit Düzeyinde Kaydırma İşleçleri
ms.date: 10/18/2018
helpviewer_keywords:
- operators [C++], bitwise
- shift operators, bitwise
- bitwise-shift operators
- operators [C++], shift
ms.assetid: d0485785-5c72-47e1-a7c0-0adde03ade23
ms.openlocfilehash: d0873e3975e69bbfac01d437006561f0bf88ee31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485364"
---
# <a name="bitwise-shift-operators"></a>Bit Düzeyinde Kaydırma İşleçleri

Kaydırma işleçleri ilk işlenen sola kaydırma (**&lt;&lt;**) sağa (**>>**) ikinci işlenenin konum sayısına göre belirtir.

## <a name="syntax"></a>Sözdizimi

*Shift-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*additive-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Shift-expression* **&lt; &lt;** *additive-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Shift-expression* **>>** *additive-expression*

Her iki işlenen de integral değerleri olmalıdır. Bu işleçlerden her zamanki aritmetik dönüşümleri gerçekleştirir; Sonuç türü dönüştürme işleminden sonra sol işlenenin türüdür.

Leftward kaydırmalar için boşaltılmış doğru bitleri 0 olarak ayarlanır. Rightward kaydırmalar için sol boşaltılmış bitler birinci işlenenin türüne dönüştürme işleminden sonra doldurulur. Tür ise `unsigned`, bunlar 0 olarak ayarlayın. Aksi takdirde, imza biti bir kopyasını ile doldurulur. Deyim taşma olmadan sola kaydırma işleçleri

```C
expr1 << expr2
```

çarpma 2 eşdeğerdir<sup>Deyim2</sup>. Sağa kaydırma işleçleri

```C
expr1 >> expr2
```

Bölüm 2 eşdeğerdir<sup>Deyim2</sup> varsa `expr1` imzalanmamış veya negatif olmayan bir değere sahip.

İkinci işleneni negatifse veya sağ işlenen büyüktür veya eşittir yükseltilen sol işlenenin bit genişliğini ise bir kaydırma işleminin sonucu tanımsızdır.

Dönüştürmeler taşma için kaydırma işleçleri sağlamaz veya dönüştürme işleminden sonra bir kaydırma işleminin sonucu birinci işlenenin türünde temsil edilemiyorsa underflow koşullar, bilgileri kaybolabilir.

```C
unsigned int x, y, z;

x = 0x00AA;
y = 0x5500;

z = ( x << 8 ) + ( y >> 8 );
```

Bu örnekte, `x` sekiz konumları sola kaydırılacak ve `y` ötelenen sağ sekiz konumları olduğu. 0xAA55 vermek ve atanan ötelenen değerleri eklenir `z`.

Negatif bir değer sağa kaydırarak aşağı yuvarlanmasını özgün yarım değeri verir. Örneğin,-253 (ikili 11111111 00000011) doğru bir bit üretir (ikili 11111111 10000001)-127 kaydırılacağı uzaklık. Bir pozitif 253 kaydırmalar sağ +126 üretmek için.

Sağa kaydırmalar imza biti korur. İmzalı bir tamsayı sağa kaydırır en anlamlı biti ayarlanmış olarak kalır. En anlamlı bit işaretsiz tamsayı sağ geçtiğinde temizlenir.

## <a name="see-also"></a>Ayrıca Bkz.

[Sol Kaydırma ve Sağ Kaydırma İşleçleri (>> ve <<)](../cpp/left-shift-and-right-shift-operators-input-and-output.md)