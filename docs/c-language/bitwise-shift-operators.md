---
title: Bit Düzeyinde Kaydırma İşleçleri
ms.date: 10/18/2018
helpviewer_keywords:
- operators [C++], bitwise
- shift operators, bitwise
- bitwise-shift operators
- operators [C++], shift
ms.assetid: d0485785-5c72-47e1-a7c0-0adde03ade23
ms.openlocfilehash: acf31fbfbe534e3f7eba1492c5aaf173fcb8b31c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326033"
---
# <a name="bitwise-shift-operators"></a>Bit Düzeyinde Kaydırma İşleçleri

SHIFT işleçleri ilk işlenenlerini Left (**&lt;**) veya Right (**>>**) ikinci işlenenin belirttiği konum sayısına göre kayar.

## <a name="syntax"></a>Sözdizimi

*SHIFT ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Toplamsal ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Shift-Expression* ** &lt; ** *toplamalı ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Shift-Expression* **>>** *toplamalı ifadesi*

Her iki işlenen de tamsayı değer olmalıdır. Bu işleçler, her zamanki aritmetik dönüştürmeleri gerçekleştirir; sonucun türü, dönüştürmeden sonra sol işlenenin türüdür.

Soltward vardiyaları için, karıştırılmış sağ bitler 0 olarak ayarlanır. Sağ taraftaki vardiyalar için, karıştırılmış sol bitler, dönüştürmeden sonra ilk işlenenin türüne göre doldurulur. Tür ise `unsigned`0 olarak ayarlanır. Aksi takdirde, bu, işaret bitinin kopyaları ile doldurulur. Taşma olmadan sola kaydırma işleçleri için, ekstresi

```C
expr1 << expr2
```

2<sup>expr2</sup>ile çarparak eşdeğerdir. Sağ kaydırma işleçleri için

```C
expr1 >> expr2
```

, imzasız veya negatif olmayan bir değere sahip 2 expr2 bölme ile eşdeğerdir.<sup>expr2</sup> `expr1`

İkinci işlenen negatif ise veya sağ işlenen, yükseltilen sol işlenenin bit cinsinden genişliğinden büyük veya buna eşitse, bir vardiya işleminin sonucu tanımsızdır.

SHIFT işleçleri tarafından gerçekleştirilen dönüşümler taşma veya yetersiz koşullar için sağlamıyor olduğundan, bir vardiya işleminin sonucu, dönüştürmeden sonra ilk işlenen türünde temsil edilemiyorsa, bilgiler kaybolabilir.

```C
unsigned int x, y, z;

x = 0x00AA;
y = 0x5500;

z = ( x << 8 ) + ( y >> 8 );
```

Bu örnekte, `x` sol sekiz konum sola kaydırdığı ve `y` sağ sekiz konumda kaydırılan. Kaydırılan değerler eklenir, 0xAA55 verir ve öğesine `z`atanır.

Negatif bir değeri sağa kaydırma, orijinal değerin yarısını yuvarlayarak aşağı yuvarlanır. Örneğin,-253 (ikili 11111111 00000011) sağa bir bit üretir-127 (ikili 11111111 10000001). Pozitif 253, + 126 üretmek için sağa kayar.

Sağ vardiyalar, işaret bitini korur. İşaretli bir tamsayı sağa kaydırdığınızda, en önemli bit ayarlanmış olarak kalır. İşaretsiz bir tamsayı sağa kaydırdığınızda en önemli bit temizlenir.

## <a name="see-also"></a>Ayrıca bkz.

[Sol Kaydırma ve Sağ Kaydırma İşleçleri (>> ve <<)](../cpp/left-shift-and-right-shift-operators-input-and-output.md)
