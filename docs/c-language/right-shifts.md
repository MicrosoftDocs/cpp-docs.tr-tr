---
title: Sağa Kaydırmalar
ms.date: 11/04/2016
ms.assetid: c878e97d-ea3c-4c6b-90a8-b1b24b2d5b19
ms.openlocfilehash: f39c1f2f49f5a8a1f3bb5eb3f21736eedf32077e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518215"
---
# <a name="right-shifts"></a>Sağa Kaydırmalar

Bir sağa kaydırma, negatif değer sonucu imzalı tamsayı türü

Negatif bir değer sağa kaydırma yarım mutlak yuvarlanan değer verir. Örneğin, imzalı `short` -253 (onaltılık 0xFF03, ikili 11111111 00000011) değerini doğru bir bit üretir (onaltılık 0xFF81, ikili 11111111 10000001)-127 kaydırılacağı uzaklık. Pozitif 253 doğru üretir +126 kaydırılacağı uzaklık.

Sağa kaydırmalar işaretli integral türlerindeki, imza biti korur. İmzalı bir tamsayı sağa kaydırır en anlamlı biti ayarlanmış olarak kalır. Örneğin, 0xF0000000 işaretli ise `int`, sağa kaydırma 0xF8000000 üretir. Negatif kaydırma `int` sağ 32 kez 0xFFFFFFFF üretir.

En anlamlı bit işaretsiz tamsayı sağ geçtiğinde temizlenir. Örneğin, 0xF000 imzalı değilse, sonuç 0x7800 olur. Kaydırma bir `unsigned` ya da pozitif `int` sağ 32 kez 0x00000000 üretir.

## <a name="see-also"></a>Ayrıca Bkz.

[Tam Sayılar](../c-language/integers.md)